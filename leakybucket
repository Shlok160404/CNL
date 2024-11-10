#include <iostream>
using namespace std;

class LeakyBucket {
private:
    int bucketSize;
    int outputRate;
    int currentSize;

public:
   
    LeakyBucket(int bucketSize, int outputRate) {
        this->bucketSize = bucketSize;
        this->outputRate = outputRate;
        this->currentSize = 0;
    }

  
    void addPacket(int packetSize) {
        if (packetSize > bucketSize) {
            cout << "Packet of size " << packetSize << " discarded. Too large!" << endl;
        } else if (currentSize + packetSize > bucketSize) {
            cout << "Packet of size " << packetSize << " discarded. Bucket overflow!" << endl;
        } else {
            currentSize += packetSize;
            cout << "Packet of size " << packetSize << " added to the bucket. Current size: " << currentSize << endl;
        }
    }

    
    void transmit() {
        if (currentSize <= outputRate) {
            cout << "Transmitting " << currentSize << " packets." << endl;
            currentSize = 0;
        } else {
            cout << "Transmitting " << outputRate << " packets. " << currentSize - outputRate << " left in bucket." << endl;
            currentSize -= outputRate;
        }
    }
};

int main() {
    int bucketSize, outputRate, packetSize;

   
    cout << "Enter bucket size: ";
    cin >> bucketSize;
    cout << "Enter output rate: ";
    cin >> outputRate;

    LeakyBucket bucket(bucketSize, outputRate);

    char choice;
    do {
        cout << "\nEnter packet size to add: ";
        cin >> packetSize;
        bucket.addPacket(packetSize);

        bucket.transmit(); 

        cout << "\nDo you want to add another packet? (y/n): ";
        cin >> choice;
    } while (choice == 'y');

    return 0;
}
