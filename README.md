## Live reproduction
[https://svelte-head-replacement-bug.vercel.app/](https://svelte-head-replacement-bug.vercel.app/)
Open the dev tools inspection, and observe the meta tags shift around when navigating to the subpage, and then back to the home page.

## Bug description
When defining a `svelte:head` segment in both the layout and page files, and navigating to a different page, the layout head segment is removed and replaced by the initially loaded page head segment.
This results in important site-wide head elements being removed, and will result in duplicated head elements when navigating back to the same page that was initially loaded.
It seems Svelte is keeping the incorrect head segment of the two for some reason.
