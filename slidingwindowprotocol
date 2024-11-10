// EXP 7: SLIDING WINDOW PROTOCOL
#include<iostream>
using namespace std;

int main() {
    int w, f, i, frames[50];
    cout << "Enter window size: ";
    cin >> w;
    cout << "\nEnter number of frames to transmit: ";
    cin >> f;

    cout << "\nEnter " << f << " frames: ";
    for (i = 0; i < f; i++)
        cin >> frames[i];

    cout << "\n\nWith sliding window protocol the frames will be sent in the following manner (assuming no corruption of frames)\n\n";
    cout << "After sending " << w << " frames at each stage sender waits for acknowledgment sent by the receiver\n\n";
    
    // Sliding window transmission
    for (i = 0; i < f; i++) {
        cout << frames[i] << " ";
        if (((i + 1) % w) == 0) {
            cout << "\nAcknowledgment of above frames sent is received by sender\n\n";
        }
    }
    if (f % w != 0) {
        cout << "\nAcknowledgment of above frames sent is received by sender\n";
    }
    
    return 0;
}
