"Explanation here..." 
The problem asks for a calendar that can schedule events while avoiding triple bookings. Specifically, it allows up to two overlapping events, but rejects any new event that would cause three or more events to overlap at any given time.
To solve this, the program needs to track:

Single bookings – all the intervals that have been booked at least once.
Double bookings – overlapping intervals where two bookings already overlap. A third booking overlapping with this would cause a triple booking, which is not allowed.
Approach
Double Booking Check:
• Before booking a new event, check if it overlaps with any intervals in doubleBook. If it does, return false to prevent a triple booking.
Record Overlapping Intervals:
• Then, check for overlaps with all single bookings in track. For each overlap, calculate the overlapping interval and add it to doubleBook, because it now becomes a double booking.
Store Single Booking:
• If the event doesn't cause a triple booking, add it to track as a valid single booking.
Complexity
Time complexity:
O(n²) for n bookings (since each booking involves comparing with previous bookings)

Space complexity:
O(n), where n is the total number of bookings.