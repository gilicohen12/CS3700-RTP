## High-level Approach

### Sender Class
The code introduces a `Sender` class for reliable data transmission using UDP with selective repeat. It establishes a connection, crafts data packets with headers and checksums, manages acknowledgments, timeouts, and dynamically adjusts the sender's window size.

### Receiver Class
The code incorporates a `Receiver` class to handle UDP data messages. It includes functionalities for message validation, sequence extraction, checksum verification, and processing unique messages. The primary loop consistently receives and processes messages, managing both corrupted and valid data. The receiver also oversees acknowledgments, ensuring accurate printing of received messages and identifying unique ones.

## Challenges Encountered

### Sender Class
The selective repeat mechanism presented challenges in coordinating acknowledgments, timeouts, and dynamically adjusting the window size. Ensuring reliable and efficient data transfer demanded lots of consideration of round-trip time, acknowledgment processing, and window adjustment strategies.

### Receiver Class
Challenges in the `Receiver` class included navigating complexities in checksum validation, identifying unique messages based on sequence numbers, and handling corrupted or missing data.

## Key Design Aspects

- **Modularity:** The code's structure, particularly within the `Sender` class, promotes modularity through well-defined methods for various tasks.
- **Dynamic Window Adjustment:** The sender dynamically adapts the window size based on unacknowledged packets, optimizing the efficiency of data transfer.
- **Checksum Validation:** The code employs SHA-1 checksums to validate the integrity of received messages, ensuring the accuracy of transmitted data.

## Testing Overview

The code undergoes rigorous testing, exploring various scenarios encompassing acknowledgment processing, timeout handling, and dynamic window adjustments. The testing suite provided by the instructor covers cases with both correct and corrupted messages, validating the reliability and robustness of the sender's data transmission.