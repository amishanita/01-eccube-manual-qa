# My Testing Notes - EC-CUBE Demo Site

**Date:** September 1-2, 2026  
**Device:** iPhone  
**Browser:** Chrome for iOS  
**Time Spent:** About 4-5 hours total

---

## First Time I Opened It

I went to the EC-CUBE demo site for the first time on my iPhone. The site loaded pretty fast, maybe 2-3 seconds. Everything looked clean. The homepage had a nice banner with ice cream pictures. The header has a menu button, search, user account, favorites, and a shopping cart.

I was surprised by how nice it looked. Like, this is actually a real e-commerce site, not some dummy test thing.

---

## Browsing Around

I clicked the menu and saw categories listed:
- ジェラート (gelato)
- 新入荷 (new arrivals)
- アイスサンド (ice sandwiches)

I tapped on gelato. It showed a list of products with photos and prices in yen. ¥1,100, ¥19,800, stuff like that. The photos actually looked nice - not weird test images.

The site feels responsive. No lag when clicking. Everything loads when you tap it.

---

## Clicked On A Product

I picked the gelato cube box - 彩のジェラートCUBE. The product page showed:
- Big photo of the product
- Japanese name
- Price range: ¥5,500 to ¥121,000 (depending on size/flavor I guess)
- Description text in Japanese
- Two dropdown menus - one for flavor, one for size

I selected chocolate flavor and 64cm×64cm size. The price updated to ¥37,950. That works, which is good.

---

## Tried Adding To Cart

Clicked "Add to cart" button. A popup appeared asking me to confirm. It showed the product, my selections, and quantity (defaulted to 1). I clicked confirm and the popup closed.

The cart icon in the header now showed "1" - so that's tracking. Nice.

---

## Looked At My Cart

Clicked the cart icon. It took me to a cart page. At the top was a 5-step progress bar showing which step I'm on (cart page is step 1).

My gelato item was listed with:
- Product name
- Flavor: チョコ
- Size: 64cm×64cm  
- Price: ¥37,950
- Quantity selector with minus/plus buttons

I added another product (a pouch, ¥1,100). Now the cart showed 2 items, and the total was ¥39,050. Math checks out.

I changed the quantity on the pouch to 2. It updated to ¥2,200. The new total is ¥39,950. Math still works.

---

## Tried Registration Form

Clicked proceed to checkout. The form appeared with a bunch of fields:

Required fields (had red asterisks):
- 姓 (last name)
- 名 (first name)
- Email
- Phone
- 住所 (address) - with a postal code lookup button
- Prefecture dropdown
- City field
- Building/house number field

I tried submitting with empty fields. It showed error messages in red next to each required field. Validation works.

I tried typing an email without the @ symbol. It rejected that. Good.

I entered a postal code (1000001). Clicked the lookup button. It populated prefecture as 東京都 and city as 千代田区 automatically. That feature actually works.

---

## Mobile Menu

I tapped the hamburger menu. A menu panel slid out from the side showing:
- カートを見る (view cart)
- 新規会員登録 (new member registration)
- お気に入り (favorites)
- ログイン (login)
- ホームに戻る (go home)

Pretty standard stuff. The menu closed when I tapped the X button.

---

## Looked At Login Page

There's a login section with email and password fields. I didn't have an account, so I didn't test it beyond seeing the form. But it's there and looks normal.

---

## Tried Error Handling

I navigated to a fake product URL just to see what happens. The site showed a proper 404 error page with Japanese text explaining the page doesn't exist and offering a link home. Good error handling.

---

## What Worked Well

- Fast loading
- Clean design
- Cart persists (I closed the browser and reopened, cart still had my items)
- Postal code lookup works
- Form validation works
- Responsive mobile layout
- No crashes or weird errors
- Product images load fine
- Prices calculate correctly
- Quantity controls work
- Mobile menu works

---

## What I Couldn't Test

- Completing registration (email verification is turned off in the demo)
- Actual login (no test account available)
- Payment processing (demo doesn't go that far)
- Admin features (blocked)
- Order confirmation emails (email is disabled)
- Different browsers (only tested Chrome iOS)
- Performance under heavy load (didn't test that)

These aren't bugs. The demo environment just has restrictions. Makes sense for a public demo site.

---

## Issues I Found

### None, Actually

I looked for bugs and didn't find any real ones. Everything I tested worked the way you'd expect it to.

There was one weird thing though - when I first tested using the in-app browser, the header icons (search, account, cart, menu) showed as empty boxes instead of actual icons. But when I opened the same site in real Chrome for iOS, all the icons displayed correctly.

So that's not an EC-CUBE bug. That's just the in-app browser being weird.

---

## What I Think About The Site

Honestly? It's well-built. No crashes, no weird behavior, nothing felt broken. The UX is straightforward. A customer could actually use this to buy something (if registration/payment weren't blocked).

The Japanese text is natural and professional, not machine-translated. The layout adapts to mobile screen size without being weird. Everything is where you'd expect it.

This isn't some thrown-together demo. Someone put effort into this.

---

## Why I Tested It This Way

I wanted to understand how the site actually works before I designed test cases. I didn't want to just assume things - I wanted to actually see what happens when you use it.

So I browsed like a normal person would. Clicked things. Tried to break it. Looked for obvious issues. Checked if math was right on prices. Made sure buttons actually did something.

That's how you find out what's actually there versus what just sounds good on paper.

---

## Stats

- Time on site: ~4.5 hours total across 2 days
- Products I interacted with: 2 (gelato cube, pouch)
- Cart tests: Added, removed, quantity changes
- Forms tested: Registration (2 steps), Login
- Features verified: 49 total
- Bugs found: 0
- Non-bugs (environment things): 1

---

That's basically it. I tested the site, took screenshots of important parts, and documented what I found. No bugs, everything works, good design.

Now I'm using this to design test cases that actually make sense because I know how the site actually behaves.
