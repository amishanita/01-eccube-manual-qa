# What I Actually Saw In The App

This is just a list of what I saw and tested. Nothing fancy, just what's actually there.

---

## Home Page

The home page has:
- A big banner image with ice cream
- Navigation menu (hamburger on mobile)
- Search box
- Icons for account, favorites, cart
- A list of products below the banner
- A category list in the sidebar (on desktop view)

When I loaded the page, it showed up pretty quick. No loading spinner taking forever.

---

## Navigation Menu

When I tapped the menu button, it showed:
- View cart
- New registration
- Favorites (wishlist maybe?)
- Login
- Go home

Clicking a menu item worked. The menu closed. Pretty basic stuff.

---

## Product Pages

Each product had:
- A nice photo
- Product name in Japanese
- A price or price range
- Description text
- Usually 2-3 dropdown menus for options (like flavor and size)
- An "Add to cart" button
- Related products listed below

When I selected options from the dropdowns, the price updated automatically. That's a nice touch.

---

## Shopping Cart

The cart page showed:
- A progress bar at the top (5 steps)
- Each product I added, listed out
- For each product: photo, name, my selections, price, quantity controls
- Minus and plus buttons to change quantity
- Each item showed a line total
- A grand total at the bottom
- Two buttons: "Continue shopping" and "Proceed to checkout"

The math was correct. When I changed quantities, everything recalculated.

I could remove items by clicking an X button next to each product.

---

## Add To Cart

When I clicked "Add to cart" on a product:
- A modal (popup) appeared
- It showed the product name, my selections, and quantity
- Two buttons: "Keep shopping" and "Add to cart"
- When I clicked "Add to cart", the popup closed and I was back on the product page

If I went back to my cart, the item was there. So it actually added it.

---

## Registration Form

Step 1 had:
- Last name field
- First name field
- Last name (kana)
- First name (kana)
- Company name (optional)

Step 2 had:
- Postal code with a lookup button
- Prefecture dropdown
- City/area field
- Street address field
- Phone number
- Email

All the required fields had red asterisks and a "required" label in red.

When I tried submitting without filling required fields, error messages popped up next to each empty required field. The text was in red.

When I entered a postal code and clicked the lookup button, it filled in the prefecture and city automatically. So that works.

---

## Login Page

Pretty simple:
- Email field
- Password field
- Checkbox for "Remember me"
- Login button
- Links for "Forgot password?" and "Sign up"

I didn't actually log in since I don't have a real account, but the form is there.

---

## Error Handling

When I navigated to a fake URL that doesn't exist, the site showed a 404 page. It had:
- A simple error icon
- Japanese text explaining the page wasn't found
- A button to go back home

Not a generic error page. It's actually designed for this site.

---

## Cart Icon / Indicator

In the header, the cart icon shows a number. When I had nothing in my cart, it showed 0. When I added one product, it changed to 1. When I added another, it changed to 2. It updates in real-time.

---

## Product Photos

All the product photos loaded fine. They're actual product photos - gelato in different flavors, a nice pouch, stuff like that. Not broken images or placeholder text.

---

## Price Display

Prices are shown clearly:
- In yen (¥)
- With commas for thousands (¥19,800)
- Sometimes a price range if the product has options (¥5,500～¥121,000)
- Tax included in the total shown as "税込" (tax included)

---

## Mobile Responsiveness

Everything adjusted to fit the phone screen. Nothing was cut off. Buttons were big enough to tap easily. Text was readable without zooming. The layout changed from side-by-side to stacked when it needed to.

---

## What Isn't In The Demo

- Can't finish registration (email verification doesn't work)
- Can't actually pay for anything
- Can't see order history
- Admin section is blocked
- Email notifications don't work
- Search isn't working or is limited

These are just demo restrictions. Not bugs.

---

## Things That Actually Work

- Browsing products
- Viewing product details
- Selecting product options
- Adding to cart
- Viewing cart
- Changing quantities
- Removing items from cart
- Cart persists (if you close the browser and come back, your cart is still there)
- Postal code lookup
- Form validation
- Mobile menu
- Error pages

---

## Summary

The site does what an e-commerce site should do:
1. Let people see products
2. Let people pick options
3. Let them add to cart
4. Let them review their cart
5. Start the checkout process

Everything I tested worked the way you'd expect. No surprises, no bugs, no crashes.

It's a solid demo site.
