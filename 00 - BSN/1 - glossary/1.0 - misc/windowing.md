# Windowing
___
> Window mechanism // Fenster Mechanismus
- Flow control mechanism
- Used to manage amount of data that can be transmitted before receiving an `ACK`
- Sender and receiver agree on specific window size
	- Max. amount of unacknowledged data that can be in transit
- Helps optimize efficient communication over networks with varying speeds & capacities
- Protocols: TCP congestion window; sliding window protocol