import java.io.*;

class FIFO {
    public static void main(String args[]) throws IOException {
        BufferedReader obj = new BufferedReader(new InputStreamReader(System.in));

        // Getting the number of frames
        System.out.print("Enter the number of frames: ");
        int f = Integer.parseInt(obj.readLine());

        // Initialize frames and pointer
        int[] frames = new int[f];
        for (int i = 0; i < f; i++) {
            frames[i] = -1;  // Initialize all frames to -1 (empty)
        }

        // Get the number of pages
        System.out.print("Enter the number of pages: ");
        int n = Integer.parseInt(obj.readLine());
        int[] pages = new int[n];

        // Get the page sequence
        System.out.println("Enter the page sequence: ");
        for (int i = 0; i < n; i++) {
            pages[i] = Integer.parseInt(obj.readLine());
        }

        int pageFaults = 0;
        int pageHits = 0;
        int pointer = 0;

        // FIFO Page Replacement Logic
        for (int i = 0; i < n; i++) {
            int page = pages[i];
            boolean pageFound = false;

            // Check if the page is already in the frames
            for (int j = 0; j < f; j++) {
                if (frames[j] == page) {
                    pageFound = true;
                    pageHits++;
                    break;
                }
            }

            // If page is not in frames, we need a page fault
            if (!pageFound) {
                frames[pointer] = page;   // Replace the oldest page
                pointer = (pointer + 1) % f;  // Move pointer in a circular fashion
                pageFaults++;
            }

            // Display the current frame status
            System.out.print("Frames: ");
            for (int j = 0; j < f; j++) {
                if (frames[j] != -1) {
                    System.out.print(frames[j] + " ");
                } else {
                    System.out.print("- ");
                }
            }
            System.out.println();
        }

        // Display final results
        System.out.println("\nTotal Page Faults: " + pageFaults);
        System.out.println("Total Page Hits: " + pageHits);
    }
}
