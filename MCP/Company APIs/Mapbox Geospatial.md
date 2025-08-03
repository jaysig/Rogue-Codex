# Mapbox Geospatial MCP Server

**Repository:** https://github.com/mapbox/mcp-server  
**Category:** Company APIs  
**Scope:** Global (recommended)  
**Type:** Geospatial Intelligence & Mapping  
**API Required:** Yes (Mapbox Access Token)

The Mapbox MCP Server enables AI applications to access geospatial intelligence by providing seamless integration with Mapbox's location APIs for geocoding, routing, and mapping capabilities.

## Key Features

- **Global Geocoding**: Convert addresses to coordinates worldwide
- **Points of Interest Search**: Find nearby businesses and landmarks
- **Multi-Modal Routing**: Calculate routes with real-time traffic data
- **Travel Time Matrices**: Analyze travel times between multiple points
- **Isochrone Generation**: Create travel time zones and reachability maps
- **Static Map Images**: Generate visual map representations

## Installation

### Prerequisites
- Node.js environment
- Mapbox access token (free account available at mapbox.com)

### Global Installation
```bash
# Install the package
npm install -g @mapbox/mcp-server

# Add to global MCP configuration
claude mcp add mapbox -- mapbox-mcp-server --token YOUR_MAPBOX_TOKEN
```

### Docker Support
```bash
# Docker deployment option available
docker run -e MAPBOX_TOKEN=your_token mapbox/mcp-server
```

## Use Cases

### AI Travel Assistants
- Route planning and optimization
- Travel time estimation
- Transportation mode comparison
- Real-time traffic integration

### Location-Based Recommendations
- Find nearby restaurants, hotels, attractions
- Discover points of interest by category
- Local business search and information

### Logistics Optimization
- Delivery route planning
- Fleet management support
- Warehouse location analysis
- Supply chain optimization

### Geospatial Data Visualization
- Create maps for presentations
- Visual route representation
- Geographic data analysis
- Location-based reporting

## Example Prompts

### Basic Searches
```
"Find coffee shops near Empire State Building"
"What are the coordinates for 123 Main St, San Francisco?"
"Show me gas stations within 5 miles of my location"
```

### Routing and Navigation
```
"Get driving directions from LAX to Hollywood"
"Calculate travel time between downtown and the airport"
"Find the fastest route avoiding highways"
```

### Visual Mapping
```
"Create a map showing route between Golden Gate Bridge and Fisherman's Wharf"
"Generate a static map of Central Park"
"Show isochrones for 30-minute drive time from Times Square"
```

## Integration Options

### Supported Platforms
- **Claude Desktop**: Direct integration
- **Visual Studio Code**: Development environment support
- **Cursor AI IDE**: Code assistant integration
- **Custom AI Agents**: API integration for custom applications

### Privacy Features
- **Local Execution**: API calls execute locally on your machine
- **No Data Storage**: Server doesn't store user location data
- **Token Security**: Mapbox API token remains on user's device

## Configuration

### API Token Setup
1. Create free Mapbox account at mapbox.com
2. Generate access token from account dashboard
3. Configure token in environment variables or MCP settings

### Rate Limits
- Free tier: 100,000 requests per month
- Paid tiers available for higher usage
- Rate limiting handled automatically

## Advanced Features

### Travel Time Analysis
- Multi-point travel time matrices
- Peak vs. off-peak time comparisons
- Transportation mode analysis

### Geofencing
- Create custom geographic boundaries
- Point-in-polygon analysis
- Location-based triggers

### Map Styling
- Custom map themes and styles
- Brand-specific map appearances
- Data visualization overlays

## Related Tools

- **Browser-use MCP**: For web-based map interaction
- **Memory MCP**: Store frequent locations and preferences
- **Make MCP**: Automate location-based workflows

---

*Last Updated: 2025-08-02*