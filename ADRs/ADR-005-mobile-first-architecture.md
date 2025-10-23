# ADR-005: Mobile-First Architecture

## Status
Accepted

## Context
Primary user interactions happen via mobile devices:
- Vehicle unlocking via NFC requires mobile app
- Photo capture for returns needs camera access
- GPS tracking for user location
- On-the-go booking while commuting
- Offline capability needed in poor connectivity areas

Mobile experience directly impacts user satisfaction and retention.

## Decision
Design all features mobile-first with progressive enhancement:
1. **Offline-First**: Core features work without connectivity
2. **Edge Computing**: Process what's possible on device
3. **Progressive Web App**: Web fallback for app store issues
4. **Native Features**: Leverage device capabilities (NFC, camera, GPS)
5. **Responsive API**: Optimize for mobile bandwidth and battery

## Consequences

### Positive
- **Better UX**: Optimized for primary use case
- **Offline Capability**: Works in tunnels, basements, poor coverage
- **Performance**: Reduced latency through edge processing
- **Battery Efficiency**: Minimized network calls
- **App Store Independence**: PWA provides backup distribution

### Negative
- **Development Complexity**: Multiple platforms to support
- **Sync Challenges**: Offline data reconciliation
- **Storage Limits**: Device storage constraints
- **Update Management**: App store approval delays
- **Feature Parity**: Desktop may have reduced features

## Alternatives Considered

### Web-Only Solution
- **Pros**: Single codebase, instant updates, no app stores
- **Cons**: No NFC access, limited offline, poor performance

### Native Apps Only
- **Pros**: Best performance, full device access
- **Cons**: Expensive development, app store dependence

### Desktop-First Design
- **Pros**: Richer interface, easier development
- **Cons**: Poor mobile experience, majority of users impacted
