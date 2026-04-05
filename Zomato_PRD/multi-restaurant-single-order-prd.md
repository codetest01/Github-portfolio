# Multi-Restaurant Single Order PRD

## Title
**Multi-Restaurant Single Order**

## Background
Zomato currently allows users to order from one restaurant per checkout. Users who want multiple cuisines or combo meals across restaurants need to place separate orders, increasing friction and reducing average order value. This feature will enable customers to add items from multiple restaurants into a single checkout flow.

---

## Objectives

### Primary goal
- Enable customers to place one consolidated order containing items from multiple restaurants.

### Business outcomes
- Increase conversion by reducing checkout friction.
- Grow average order value and basket size.
- Increase cross-restaurant sales and partner restaurant exposure.
- Improve customer satisfaction for group orders and multi-cuisine occasions.

---

## Success metrics

### Key metrics
- Conversion rate for multi-restaurant orders
- Average order value (AOV) uplift
- Cart abandonment rate reduction
- Time-to-checkout for multi-restaurant flows
- Repeat usage rate for multi-restaurant checkout

### Supporting metrics
- Number of restaurants per order
- Incremental commission revenue
- Customer satisfaction / NPS for the new flow

---

## Scope

### In scope
- Add-to-cart support for multiple restaurants in one checkout.
- Unified cart and checkout experience.
- Restaurant-specific preparation and delivery time estimates.
- Delivery fee calculation for multi-restaurant orders.
- Order routing to multiple kitchens with separate restaurant receipts.
- Customer-facing segmentation of items by restaurant in cart.
- Order tracking for multi-restaurant fulfillment stages.
- Merchant and courier workflows to support multi-restaurant orders.

### Out of scope (initial launch)
- Multi-restaurant orders across non-compatible delivery zones by a single courier.
- Complex promotions or cross-restaurant combos in phase 1.
- Dine-in / pickup multi-restaurant experience.
- Multi-restaurant orders with mixed delivery partners outside current arrangements.

---

## User personas

### Urban foodies
- Want to order different cuisines for a group.
- Prefer one checkout over multiple orders.

### Families / shared households
- Need multiple restaurant items in one order for convenience.

### Office teams
- Want a single payment and receipt for team lunch across restaurants.

### Frequent users
- Seek variety and streamlined ordering.

---

## User problems

- “I want a pizza and sushi in one order without placing two checkouts.”
- “Managing multiple orders and payments is cumbersome.”
- “Tracking multiple deliveries separately is confusing.”
- “Delivery charges multiply when ordering from different restaurants.”

---

## User stories

### As a customer
1. I want to add items from different restaurants into one cart.
2. I want to see the cart grouped by restaurant.
3. I want to pay once and receive one consolidated order confirmation.
4. I want delivery fees and ETAs clearly shown per restaurant.
5. I want to track the progress of each restaurant’s preparation and delivery.
6. I want to know if any item cannot be combined before checkout.
7. I want receipts that show itemization per restaurant.

### As a courier
1. I want to see all restaurants and pickup instructions in one route.
2. I want separate pickup timestamps or slots per restaurant if required.

### As a restaurant partner
1. I want to receive a clear order receipt for my items only.
2. I want accurate preparation time and delivery assignment data.

### As a product owner
1. I want the feature to work within delivery zone constraints.
2. I want the feature to capture incremental revenue and user behavior.

---

## Functional requirements

### 1. Cart and item selection
- Allow users to browse and add items from multiple restaurants in the same session.
- Persist multi-restaurant cart across app sessions.
- Show clear restaurant headers in cart.
- Display each restaurant’s minimum order value, delivery fee, and ETAs.
- Disable checkout if selected restaurants are not combinable due to zone or timing.

### 2. Delivery and logistics
- Calculate total delivery fee by summing restaurant-specific fees, plus any multi-restaurant surcharge if needed.
- Show each restaurant’s estimated food preparation time and separate delivery milestones.
- Determine whether one courier can serve all restaurants or if separate couriers are required.
- If not possible, either prevent combination or transparently show separate deliveries.

### 3. Checkout and payment
- Single checkout flow with consolidated payment.
- Apply promotions and discounts per restaurant and across the overall order where allowed.
- Display split order summary by restaurant before payment.
- Generate a single order number with internal sub-order IDs by restaurant.

### 4. Order confirmation and tracking
- Provide a single confirmation screen and notification.
- Track item status by restaurant within one order.
- Show pickup and delivery status for each restaurant segment.
- Send consolidated notifications for order milestones and exceptions.

### 5. Restaurant and partner integration
- Send separate order receipts to each restaurant for their items.
- Support kitchen systems with multi-restaurant sub-orders.
- Share courier pickup instructions and timings that reflect multiple restaurant pickups.

### 6. Edge cases and validation
- Prevent addition of items from restaurants with incompatible delivery zones/time windows.
- Handle menu item changes, stockouts, and unavailability separately for each restaurant.
- Support removal of restaurant segments or items without invalidating the full order if possible.
- Provide clear error messaging for conflicts such as:
  - “Item unavailable”
  - “Restaurant not reachable by same courier”
  - “Delivery window mismatch”

---

## User experience and flows

### Primary flow
1. User searches or browses restaurants.
2. User adds items from Restaurant A.
3. User continues shopping and adds items from Restaurant B.
4. Cart shows grouped sections: Restaurant A, Restaurant B.
5. Cart summary displays combined total, delivery fees, and ETAs.
6. User taps checkout.
7. Payment screen shows consolidated total and restaurant-specific details.
8. User pays once.
9. Order confirmation screen shows one order and sub-orders.
10. Tracking screen shows per-restaurant progress.

### UI details
- “Add from another restaurant” CTA in cart.
- Cart badge/indicator showing “2 restaurants”.
- Restaurant chip or badge for each cart section.
- Clear labeling of fees and ETAs per restaurant.
- Warning state if any restaurant item causes checkout restrictions.

### Mobile/desktop considerations
- Mobile: collapsible restaurant sections in cart.
- Desktop: side-by-side order summary and restaurant breakdown.

---

## Non-functional requirements

### Performance
- Cart and checkout latency must remain under acceptable thresholds.
- Multi-restaurant order creation should not exceed baseline order creation time by more than 20%.

### Scalability
- Support increased order complexity (many users with multi-restaurant carts).
- Backend should handle sub-order creation and routing.

### Reliability
- Orders must still be fault-tolerant when one restaurant fails; if failure occurs, user gets a clear resolution path.
- Events and status updates should remain consistent across split order segments.

### Security
- Payment flow remains PCI compliant.
- User data and order details are protected as normal.

---

## Dependencies

- Restaurant availability and delivery zone services
- Courier routing and assignment system
- Checkout and order management backend
- Merchant receipt / kitchen printing integration
- Cart persistence services
- Promotions engine

---

## Assumptions

- Multiple restaurants can be combined only when within overlapping delivery zones and time windows.
- Zomato can allocate couriers across multiple pickups in one route.
- Restaurant partners accept receiving sub-orders via existing order systems.

---

## Risks

- Increased operational complexity for courier routing and pickup coordination.
- User confusion if fee/ETA details are unclear.
- Restaurant partners may be reluctant if sub-order handling is not seamless.
- Edge cases where one restaurant delays can degrade the whole order experience.

---

## Rollout plan

### Phase 1: Pilot
- Launch to a limited set of users in dense delivery zones.
- Select partner restaurants with similar preparation times.
- Validate logistics and user behavior.

### Phase 2: Expand
- Add more restaurants and broader zones.
- Introduce promotional incentives for multi-restaurant orders.

### Phase 3: Optimization
- Add cross-restaurant bundle deals.
- Improve delivery fee optimization and courier grouping.
- Add support for mixed delivery partners or multiple couriers if needed.

---

## Success criteria

- Multi-restaurant orders show positive impact on AOV and conversion.
- Customer satisfaction for the new flow reaches target benchmarks.
- Courier pickups and restaurant receipts process reliably in at least 90% of orders during pilot.
- Feature is stable enough for broader rollout after pilot.

---

## Appendix

### Example order structure
- Order ID: `ZMT12345`
  - Restaurant A sub-order
  - Restaurant B sub-order
  - Combined payment
  - Unified tracking

### Example copy
- Cart label: “Your order from 2 restaurants”
- Checkout warning: “Delivery time reflects the longest kitchen prep + combined delivery route.”
- Empty state: “Add items from another restaurant to create a multi-restaurant order.”
