#include <iostream>
using namespace std;

const int WINDOW_SIZE = 4; // Sender's window size

void sendFrame(int frame) {
    cout << "Sending frame: " << frame << endl;
}

void goBackN(int numFrames) {
    int base = 0;
    int nextSeqNum = 0;

    while (base < numFrames) {
        // Send frames in the window
        while (nextSeqNum < base + WINDOW_SIZE && nextSeqNum < numFrames) {
            sendFrame(nextSeqNum);
            nextSeqNum++;
        }

        // Simulate acknowledgment for the first frame in the window
        int ack;
        cout << "Enter the Ack for frame " << base << ": ";
        cin >> ack;

        // If acknowledgment is received, move the base
        if (ack == base) {
            base++;
        }
    }
    cout << "All frames transmitted successfully!" << endl;
}

int main() {
    int numFrames;
    cout << "Enter number of frames: ";
    cin >> numFrames;

    goBackN(numFrames);

    return 0;
}
