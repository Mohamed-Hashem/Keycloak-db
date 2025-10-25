# Keycloak Theme Database

A simple JSON database for managing Keycloak realm themes and configurations.

## API Endpoint

**Base URL:** `https://api.jsonbin.io/v3/b/68fcafe1d0ea881f40baa2ae`

Access the theme database via the JSONBin API.

## Structure

The database contains multiple realms, each with their own theme variations:

```json
{
    "RealmName": {
        "displayName": "Display Name",
        "themes": {
            "ThemeName": {
                "primaryTextColor": "#HEX",
                "primaryBgColor": "#HEX",
                "backgroundColor": "#HEX",
                "logo": "data:image/jpeg;base64,..."
            }
        }
    }
}
```

## Current Realms

-   **Medad** - "New Medad" - Educational platform with distinct color schemes
-   **Naseej** - Enterprise platform with modern professional themes

## Theme Variants

Each realm includes two theme variants:

### Medad Themes

-   **Cat** - Blue primary with light backgrounds
    -   Primary BG: `#4A90E2` (Sky Blue)
    -   Background: `#F5F7FA` (Light Blue-Grey)
    -   Text: `#2C3E50` (Dark Blue-Grey)
-   **Dog** - Orange/Gold primary with warm backgrounds
    -   Primary BG: `#F5A623` (Golden Orange)
    -   Background: `#FFFBF0` (Warm Cream)
    -   Text: `#4A4A4A` (Charcoal)

### Naseej Themes

-   **Cat** - Purple primary with clean white backgrounds
    -   Primary BG: `#8E44AD` (Purple)
    -   Background: `#FAFAFA` (Off-White)
    -   Text: `#34495E` (Dark Slate)
-   **Dog** - Vibrant orange primary with subtle backgrounds
    -   Primary BG: `#E67E22` (Bright Orange)
    -   Background: `#FFF5EE` (Seashell White)
    -   Text: `#2C2C2C` (Near Black)

## Usage

Load the `db.json` file or access via API to retrieve theme configurations for different realms and apply them to your Keycloak instance.

### API Usage Example

```javascript
fetch("https://api.jsonbin.io/v3/b/68fcafe1d0ea881f40baa2ae")
    .then((response) => response.json())
    .then((data) => {
        const medadCatTheme = data.record.Medad.themes.Cat;
        // Apply theme colors to your application
    });
```

## Theme Properties

-   `primaryTextColor` - Primary text color for the theme
-   `primaryBgColor` - Primary background/brand color
-   `backgroundColor` - Page/container background color
-   `logo` - Base64 encoded image data (JPEG/PNG format)
