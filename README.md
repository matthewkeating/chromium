# Usage
These files allow you to create tabbed PWAs.

## Prerequisites
A Chromium-based browser like Chrome, Edge, or Brave.

## Instructions
1. Launch your browser.
2. Navigate to your browser's flag configuration (e.g., `edge://flags`).
3. Search for, and enable, the `Desktop PWA tab strips` feature.
4. Search for, and enable, the `Mac PWA notification attribution` feature.
5. Restart your browser.
6. Install the Requestly extension.
7. Follow the rules for the different sites below.

### Claude
Claude is straightforward. Simply add a new HTTP interceptor rule of type Redirect Request. Configure it as shown below.

![[claude.png]]

Save the rule, navigate to http://claude.ai, install the app.

### GitHub
GitHub is more complicated. To get it working, I installed 4 Requestly rules:

One Redirect Request rule.

![[github-redirect.png]]

Three Modify Headers rules.

![[github-csp.png]]

![[github-cors.png]]

![[github-content-type.png]]

Once the rules are created, navigate to http://github.com, install the app.

## Limitations

1. There is a bug in Chromium's PWA experience that prevent Cmd+T from opening a new tab. New tabs can only be open using the + symbol in the tab bar.
2. The tab bar colors are static and don't always look good in light OR dark mode. You can play with adding. "theme_color" and "background_color" to the manifest, but I did not.
