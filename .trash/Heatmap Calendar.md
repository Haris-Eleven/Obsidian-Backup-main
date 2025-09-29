```dataviewjs // PS. remove backslash \ at the very beginning!
dv.span("** 🗓️ CP questions Heatmap **")

const calendarData = {
	year: 2025,  // Adjust as needed
	colors: {
		blue:        ["#8cb9ff", "#69a3ff", "#428bff", "#1872ff", "#0058e2"],
		green:       ["#c6e48b", "#7bc96f", "#49af5d", "#2e8840", "#196127"],
		red:         ["#ff9e82", "#ff7b55", "#ff4d1a", "#e73400", "#bd2a00"],
		orange:      ["#ffa244", "#fd7f00", "#dd6f00", "#bf6000", "#9b4e00"],
		pink:        ["#ff96cb", "#ff70b8", "#ff3a9d", "#ee0077", "#c30062"],
		orangeToRed: ["#ffdf04", "#ffbe04", "#ff9a03", "#ff6d02", "#ff2c01"]
	},
	showCurrentDayBorder: true,
	defaultEntryIntensity: 4,
	intensityScaleStart: 10,
	intensityScaleEnd: 100,
	entries: [],
}

// Iterate over all pages in "Daily Notes" that have the 'exercise' field
for (let page of dv.pages('"Daily Notes"').where(p => p.exercise)) {
	// page.file.path is like "Daily Notes/2025/July/07-Monday"

	const pathParts = page.file.path.split("/")
	const year = pathParts[pathParts.length - 3]
	const month = pathParts[pathParts.length - 2]
	const dayPart = pathParts[pathParts.length - 1]  
	const dayNumber = dayPart.split("-")[0]
	const dateString = `${year}-${month}-${dayNumber}`

	const months = {
		January: "01", February: "02", March: "03", April: "04",
		May: "05", June: "06", July: "07", August: "08",
		September: "09", October: "10", November: "11", December: "12"
	}
	const monthNumber = months[month]

	const formattedDate = `${year}-${monthNumber}-${dayNumber}`

	calendarData.entries.push({
		date: formattedDate,    
		intensity: page.CP, 
		content: "🏋️",           
		color: "orange",
	})
}

renderHeatmapCalendar(this.container, calendarData)

```