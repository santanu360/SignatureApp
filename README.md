# Signature App

This project is a web-based application that allows users to draw, save, and retrieve their signatures. The application provides options to customize the text color, background color, and font size of the signature. Users can clear the canvas, save their signature as an image, and retrieve previously saved signatures.

## Features

- **Text Color Picker**: Allows users to select the color of the text they draw on the canvas.
- **Background Color Picker**: Allows users to change the background color of the canvas.
- **Font Size Selector**: Provides options to change the font size of the text drawn on the canvas.
- **Clear Button**: Clears the canvas.
- **Save & Download Button**: Saves the current state of the canvas and allows users to download it as an image.
- **Retrieve Saved Signature Button**: Retrieves and displays a previously saved signature from local storage.

## Technologies Used

- HTML
- CSS
- JavaScript
- Bootstrap

## How to Use

1. Open the application in a web browser.
2. Use the color pickers to select the text and background colors.
3. Use the font size selector to choose the desired font size.
4. Draw on the canvas using the mouse.
5. Click the "Clear" button to clear the canvas.
6. Click the "Save & Download" button to save the current signature and download it as an image.
7. Click the "Retrieve Saved Signature" button to retrieve and display a previously saved signature.

## Project Explanation

This project is a simple web application designed to allow users to create and manage their digital signatures. The main components of the application include a canvas element for drawing, input elements for customizing the drawing, and buttons for clearing, saving, and retrieving signatures.

The canvas element is used to capture the user's drawing using mouse events. The application listens for `mousedown`, `mousemove`, and `mouseup` events to draw lines on the canvas. The color and font size of the drawing can be customized using the color pickers and font size selector.

The "Clear" button clears the canvas by calling the `clearRect` method on the canvas context. The "Save & Download" button saves the current state of the canvas to local storage and allows the user to download it as an image. The "Retrieve Saved Signature" button retrieves the saved signature from local storage and displays it on the canvas.
