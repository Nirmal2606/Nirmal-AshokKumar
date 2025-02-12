Collapsible Sectioned List with Reverse Order in SwiftUI

This SwiftUI app displays a collapsible, sectioned list of cities grouped by admin_name. It includes a "Reverse Order" button to toggle the display order of the sections and items.

Features

Collapsible Sections: Each section is expandable and collapsible. Dynamic Data: The list is populated from a au_cities.json file. Reverse Order: A button allows toggling the order of items between normal and reversed. Clean UI: Built with SwiftUI using DisclosureGroup and List. Requirements Xcode 14.0 or later iOS 15.0 or later

Setup Clone the repository or copy the project files into your Xcode project.

Add a au_cities.json file to the project's main bundle. The JSON should contain an array of city objects in the following format:

[ { "city": "Sydney", "lat": "-33.8678", "lng": "151.2100", "country": "Australia", "iso2": "AU", "admin_name": "New South Wales", "capital": "admin", "population": "4840600", "population_proper": "4840600" }, { "city": "Melbourne", "lat": "-37.8136", "lng": "144.9631", "country": "Australia", "iso2": "AU", "admin_name": "Victoria", "capital": "admin", "population": "4529500", "population_proper": "4529500" } ]

Run the app in Xcode using the iOS Simulator or a physical device.

How It Works Data Loading: The app loads city data from a local JSON file (au_cities.json) at launch. The JSON is decoded into a Swift model using Codable.

Collapsible List: The cities are grouped by their country property and displayed in sections. Each section can be expanded or collapsed using DisclosureGroup.

Reverse Order: Clicking the "Reverse Order" button toggles the isReversed state. When reversed, both the section order and the items within each section are displayed in reverse.

Code Overview City Model

The CityModel struct represents a single city and conforms to Codable:

struct City: Identifiable, Codable { let id = UUID() let city: String let lat: String let lng: String let country: String let iso2: String let admin_name: String let capital: String let population: String let population_proper: String }

Content View: This is the primary view that displays the list. Key features include:

DisclosureGroup for collapsible sections. Button to reverse the order of sections and items. JSON data loading using Bundle.main.url. Key Features Grouped and Dynamic Sections The cities are grouped dynamically by their country field using Dictionary(grouping:by:).

Reverse Functionality The reverse functionality dynamically updates the order of both sections and their items without affecting the original data.

Future Enhancements

Add a search bar for filtering cities. Support additional sorting options (e.g., by population or name). Fetch city data from a remote API instead of a local JSON file.

License This project is open-source and available
