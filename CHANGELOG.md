# Changelog

## 0.1.0-rc.1

### Enhancements
  * Added Shared Event Handlers which are global event handlers shared among all pages.
    That's a simple model to work with where a layout, component, or multiple pages may share the same event handler,
    for example a newsletter subscription form in a component called in a layout doesn't need to duplicate the same
    event handler in all pages.

### Breaking Changes
  * Remove Page Event Handlers in favor of Shared Event Handlers.
    With Shared Event Handlers, it doesn't make sense to have page event handlers unless overriding becomes a neccessity.
    The data is automatically migrated in a best-effort way, duplicated event handler names (from multiple pages) are
    consolidated into a single shared event handler. See the migration `V002` for more info.

## 0.1.0-rc.0 (2024-08-02)

### Enhancements
  * Loader to fetch resources from DB and compile modules
  * Media Library to upload and serve images and other media
    * Built-in Repo (DB) and S3 storage
    * Post-process images to optimized .webp format
  * Error Page to handle failures and display custom pages
    * Pre-defined 404 and 500 pages
  * Components
    * Pre-defined set of default components
    * Support attrs and slots
    * Support for Elixir and HEEx parts
  * Layouts
    * Pre-defined default layout
    * Meta tags
    * Resource links
    * Revisions
  * Pages
    * Pre-defined default home page
    * Meta tags
    * Schema.org support
    * Events (handle_event)
    * Revisions
  * Snippets (liquid template)
    * Page title
    * Meta tags
  * Stylesheets
  * Live Data to define and manage assigns at runtime
    * Support Elixir and text content
  * Custom Page fields to extend the Page schema
  * Router helper `~p` to generate paths with site prefixes
  * Content management through the `Beacon.Content` API
  * A/B Variants
  * TailwindCSS compiler
  * `@beacon` read-only assign
  * mix task `beacon.install` to bootstrap a new Beacon site
  * Lifecycle hooks to inject custom logic into multiple layers of the process
