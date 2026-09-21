# Booking Lab Evidence Record

**Name:** Samawarin Phakdeewanit

**Student ID:** 6681338 

**Repository:** https://github.com/psamawarin/iccs471-booking-lab-Samawarin-Pha

## Goal
The function create_booking is changed so any bookings that overlap an existing booking raise ValueError.


## Constraints / Out of Scope
booking.py and test_booking.py were allowed to change. On the other hand the current tests, validation rules, any configuration or starter files have to remain the same.


## Key Decision and Agent Claim

Copilot suggested to add a same-room overlap check before the append. The logic for checking overlap were added to create_booking. No other files other than booking.py and test_booking.py had any changes suggested.

I inspected the changes made in booking.py and test_booking.py to make sure behavior is as expected. booking.py checks and rejects ejects same-room overlaps. Test cases were added to test_booking.py to check this.


## Verification: Claim → Evidence
- **Claim:** A booking cannot overlap an existing booking
- **Command or test I ran:** uv run python -m unittest discover -s tests -v
- **Actual result:** test_rejects_overlapping_booking_in_same_room ... ok
- **What this supports:** Any new bookings that overlap existing booking will be rejected

## Manual Validation
When demo.py was ran, Overlapping booking in room A is now rejected and the error message is printed. Stored bookings is also correct at 3 now since the overlapping room is rejected.

## Remaining Uncertainty
There are no checks to see if rooms are valid. Currently it only checks if it is empty.