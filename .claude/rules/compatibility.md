# Compatibility Rules

## Device Support Strategy

### iOS-Only Development
- **iOS Only**: This is a native iOS Swift app with no Android plans
- **Native iPhone and iPad Support**: Must natively support both iPhone and iPad from the beginning
- **Unified UI Architecture**: UI components, layout, views, constants, spacing, and ratios should work seamlessly on both device types

### Device Support
- **iPhone**: Primary target device
- **iPad**: Full native support (not compatibility mode)
- **Universal Layout**: Design UI architecture to prevent iPhone layout changes from breaking iPad layout and vice versa

### Orientation
- **Portrait Mode Only**: App must remain in portrait orientation on both iPhone and iPad
- **No Rotation Support**: App does not rotate when device rotates - it stays locked in portrait
- **No Landscape Support**: Do not implement landscape layouts or functionality

### iOS Version Support
- **Minimum iOS Version**: iOS 15.0
- **Forward Compatibility**: Support all iOS versions after iOS 15
- **API Usage**: Use APIs available in iOS 15+ only
- **Deprecation Check**: Avoid deprecated APIs that may be removed in future iOS versions

### Screen Size Support
- **iPhone Models**: Must support iPhone 14, 15, 16 and their Pro/Max variations with different screen sizes
- **iPad Models**: Must support all iPad models including iPad Pro 13" M4, iPad 10th gen, iPad mini 6, and other variants
- **Adaptive Layout Strategy**: Use Auto Layout, Size Classes, and constraints to create truly adaptive layouts
- **No Device-Specific Code**: MUST NOT use conditional code like "if iPad then..." or "if older_iPad then..." 
- **Universal Design**: UI layout/view code must work seamlessly across all screen sizes from day 1
- **Constraint-Based**: Rely on constraint-based layout system rather than hardcoded dimensions

## Development Best Practices

### Code Architecture
- **Swift Native**: Use native Swift with Xcode
- **Separation of Concerns**: Keep business logic separate from UI code
- **Protocol-Oriented**: Use protocols for abstraction where appropriate
- **Configuration-Driven**: Use configuration files for device-specific settings

### UI/UX Guidelines
- **Responsive Design**: Design for various screen sizes within portrait orientation
- **Touch Targets**: Ensure minimum 44pt touch targets for accessibility
- **Safe Areas**: Respect safe areas on both iPhone and iPad
- **Navigation**: Use native iOS navigation patterns
- **Adaptive Layout**: Use Auto Layout and Size Classes for iPhone/iPad adaptation

### Testing Requirements
- **iOS Testing**: Test on iOS 15+ devices/simulators
- **Device Testing**: Test on various iPhone screen sizes and iPad models
- **Orientation Testing**: Verify app stays in portrait mode during rotation
- **Background Mode**: Test background audio recording functionality

## Technology Stack

### Primary Framework
- **Native iOS**: Swift with Xcode
- **UIKit**: For UI components and navigation
- **Core Audio**: For audio recording and analysis
- **Core Data**: For local data persistence
- **CloudKit**: For iCloud sync (app-private container)

### iOS Best Practices
- **Swift**: Modern Swift syntax and features
- **MVC/MVVM**: Use appropriate architectural patterns
- **Storyboards/XIBs**: Use Interface Builder for UI layout
- **Auto Layout**: For responsive design across devices
- **Background Modes**: Configure for background audio recording

### Development Tools
- **Xcode**: Primary IDE
- **Simulator**: For testing on various devices
- **Instruments**: For performance monitoring and debugging
- **TestFlight**: For beta testing

### Key Frameworks & APIs
- **AVAudioEngine**: For audio recording and processing
- **AVAudioSession**: For managing audio session
- **Core Data**: For local data storage
- **CloudKit**: For iCloud synchronization
- **UserNotifications**: For local notifications if needed

## Anti-Patterns to Avoid

❌ **iPhone-Only Assumptions**: Assuming iPhone-specific screen sizes or behaviors
❌ **Hardcoded Dimensions**: Using fixed dimensions that don't adapt to different screen sizes
❌ **Landscape Dependencies**: Creating layouts that depend on landscape mode
❌ **Deprecated APIs**: Using deprecated iOS APIs
❌ **Memory Leaks**: Not properly managing audio recording resources
❌ **Background Limitations**: Not properly handling background audio recording constraints 