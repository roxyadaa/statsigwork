# Statsig Integration Demo

## Overview
This project demonstrates the integration of Statsig analytics into a modern landing page. It showcases various event tracking capabilities and feature management using Statsig's JavaScript SDK.

## Project Structure
- `index.html` - Main landing page with Statsig integration
  - Beautiful, responsive design with gradient effects
  - Feature cards with hover animations
  - Call-to-action button with smooth transitions

## Statsig Integration Steps

### 1. SDK Installation
```html
<script src="https://cdn.jsdelivr.net/npm/@statsig/js-client@3/build/statsig-js-client+session-replay+web-analytics.min.js"></script>
```

### 2. Client Initialization
- Implemented manual initialization using `StatsigClient`
- Added session replay and auto-capture features
- Configured development environment settings
- Implemented proper error handling

```javascript
const { StatsigClient, runStatsigAutoCapture, runStatsigSessionReplay } = window.Statsig;
const client = new StatsigClient(
    'CLIENT_API_KEY',
    { 
        userID: 'test-user-' + Date.now(),
        environment: { tier: 'development' }
    }
);
```

### 3. Event Tracking Implementation
The following events are tracked:

1. **Page View Event**
   - Triggers when the page loads
   - Captures:
     - Page name
     - Timestamp

2. **CTA Button Click Event**
   - Triggers when "Explore Features" is clicked
   - Captures:
     - Button name
     - Location in page

3. **Feature Card Hover Events**
   - Triggers when users hover over feature cards
   - Captures:
     - Card title
     - Interaction type

### 4. Additional Features
- Session replay enabled for detailed user interaction analysis
- Auto-capture enabled for automatic event tracking
- Async initialization with proper error handling
- Development environment configuration

## Testing
To test the integration:
1. Open the page in a browser
2. Open browser developer tools (F12)
3. Check the console for initialization messages
4. Interact with page elements to see events being logged

## Future Enhancements
- Add A/B testing capabilities
- Implement feature flags for gradual rollouts
- Add more detailed user properties
- Implement custom metrics tracking

## Technical Requirements
- Modern web browser
- Internet connection for Statsig SDK loading
- No additional dependencies required
