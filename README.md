# Chess Position Recognition from Screenshots

This project provides a powerful and efficient solution for recognizing chess positions directly from screenshots. By leveraging advanced computer vision techniques, it can accurately identify the placement of all pieces on the board. The system is particularly well-suited for online chess platforms like lichess.com and can be extended to support others.

## How it Works

The core of this project is a sophisticated computer vision algorithm that uses **template matching** to identify the individual pieces on a chessboard. Template matching is a powerful technique for finding a small image (the template) within a larger one. In this case, we have templates for each chess piece (e.g., a white pawn, a black knight), and the larger image is the chessboard screenshot.

However, template matching can be computationally expensive, especially when applied to the entire board. To address this, we've implemented a highly effective optimization: the **empty square check**.

### The Empty Square Check Optimization

Instead of immediately searching for pieces, we first identify all the empty squares on the board. This is a much faster operation. By eliminating the empty squares from our search, we can focus the more resource-intensive template matching process only on the squares that actually contain pieces.

This optimization has proven to be incredibly successful, leading to a **99% accuracy rate on lichess.com** while significantly reducing processing time.

The system is designed to be extensible. By creating new sets of templates, it can be adapted to recognize chess positions on other websites like chess.com.

## How to Run

To get the project running, follow these simple steps:

1.  **Copy the `main_file`:** Ensure that the `main_file` is in the same directory as the testing project.
2.  **Run the testing project:** Open and run the `testing_project.ipynb` file. This will execute the chess position recognition logic.

That's it! The project should now be running and recognizing chess positions.

## Future Improvements

This project has a solid foundation and can be extended in several exciting ways:

*   **Support for More Chess Websites:** The template matching approach is highly adaptable. By creating new sets of templates for the unique piece designs of other chess websites (like chess.com), the system's capabilities can be easily expanded.
*   **Real-time Recognition:** The current implementation processes static screenshots. A future version could be adapted to analyze a live video feed of a chess game, providing real-time position recognition.
*   **Automated Template Generation:** The process of creating new templates could be automated. A script could be developed to automatically extract piece images from a website's assets, making it much faster to add support for new platforms.
