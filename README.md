# Step 0: Confirm that cookies are still working (run a single "checked" test to save time).

Try testing the "checked out" page by running:
`backstop reference --filter=Checked`
And then:
`backstop test --filter=Checked`
If the tests show that the user isnt' logged in, update the cookies using the "Cookie Inspector" plugin.

- After logging into https://www.richlandlibrary.com/user/18998/checked-out inspect the page, and click on the "cookies" tab.
- Right-click on any cookie and choose "Export all cookies".
- Copy/Paste the new values in the cookies.json file.
- Repeat the above steps for https://dev-richland-site.pantheonsite.io/user/18998/checked-out
- Once all cookies for both the .richlandlibrary.com and .dev-richland-site domains have been updated, rerun the reference and test commands from step 0.

# Step 1: Create New Reference Files for all tests

`backstop reference`
This command takes snapshots from RichlandLibrary.com

# Step 2: Run Tests

`backstop test`
This takes snapshots from staging, and compares them to the reference snapshots from step 1.

# Filtering by label name

The following will filter by any label with "Search" in it.
`backstop reference --filter=Search`
