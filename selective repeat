#include <iostream>
using namespace std;

const int WINDOW_SIZE = 4; // Sender's window size

void sendFrame(int frame) {
    cout << "Sending frame: " << frame << endl;
}

void selectiveRepeat(int numFrames) {
    bool acked[numFrames] = {false}; // Track acknowledgments

    int nextSeqNum = 0;

    while (nextSeqNum < numFrames) {
        // Send frames in the window
        sendFrame(nextSeqNum);
        nextSeqNum++;

        // Simulate acknowledgment for the frames
        int ack;
        cout << "Enter Ack for the last sent frame (0 to " << numFrames-1 << "): ";
        cin >> ack;

        // Mark the frame as acknowledged
        if (ack >= 0 && ack < numFrames) {
            acked[ack] = true;
        }

        // If the frame is acknowledged, move forward
        while (acked[0]) {
            // Shift the window
            for (int i = 1; i < numFrames; i++) {
                acked[i - 1] = acked[i];
            }
            acked[numFrames - 1] = false; // Reset the last slot
        }
    }
    cout << "All frames transmitted successfully!" << endl;
}

int main() {
    int numFrames;
    cout << "Enter number of frames: ";
    cin >> numFrames;

    selectiveRepeat(numFrames);

    return 0;
}
