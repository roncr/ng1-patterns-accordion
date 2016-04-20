# AngularJS Patterns - Accordion

The accordion pattern is a simple pattern, usually composed by 2 directives, a parent/wrapper directive and then a directive use by the children.

The parent directive performs the role of managing the communication between the child directives, it is the single point of contact, the children cannot talk between them, only through the parent.

This is achieved by the child nodes registering them self into the parent, in order to do that, the child directive uses the `require` property to indicate a dependency in the parent controller, AngularJS will inject the controller of the parent into the link function of the child directive, the child directives uses this controller to register into the parent.

Then one the child has an event that needs to communicate, it uses the same reference to the parent controller to do so. The parent controller has knowledge and access to its children, hence it can pass the message across the children.

This pattern is commonly found in accordions and tabs components.

## Usage

    // index.html
    <accordion>
        <accordion-section section-title="Section A">
            Lorem ipsum
        </accordion-section>
        <accordion-section section-title="Section B">
            Foo bar
        </accordion-section>
        <accordion-section section-title="Section C">
            Hello World!
        </accordion-section>
    </accordion>

## Tasks

To run the app, simply:

    npm start

#### Disclaimer

This is a mini-project intended only as an example of the accordion pattern. This project lacks of structure and good practices, it is not either a complete implementation of a accordion component.