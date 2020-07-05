<!-- Zrobić form z inputami z animacją jak z material design. -->
<!-- https://codepen.io/maheshambure21/pen/EozKKy -->
<!-- Zrobić border i animację wypełniającą border? -->
<form class="form" action="/" method="POST">
    <h2 class="form_title">Contact Me</h2>
    <div class="form_row">
        <label class="form_label" for="name" title="name">
            <span class="form_label-text">Name</span>
            <input class="form_input" id="name" name="name" type="text">
        </label>
        <label class="form_label" for="email" title="email">
            <span class="form_label-text">Email</span>
            <input class="form_input" id="email" name="email" type="email">
        </label>
    </div>
    <label class="form_label" for="message" title="message">
        <span class="form_label-text">Message</span>
        <input class="form_input" id="message" name="message" type="text">
    </label>
    <button class="form_submit" type="submit">Send</button>
</form>

<style>
    .form {
        display: flex;
        flex-direction: column;

        padding: 2rem;
        
        border-radius: 5px;

        box-shadow: 5px 5px 21px 9px rgba(0, 0, 0, 0.34);

        background-color: #181818;
    }

    .form_row {
        display: flex;
    }

    .form_row .form_label {
        flex-grow:1;
        margin-right: 1rem;
    }

    .form_row .form_label:last-child {
        margin-right: 0;
    }

    .form_title {
        font-size:2rem;
        margin-bottom: 1rem;
    }

    .form_label {
        position: relative;

        margin-bottom: 1.25rem;
    }

    .form_label-text {
        position: absolute;
        top:0;
        left:0;
        transition:0.3s transform;
        transform-origin: left center;
    }

    .form_label:after, .form_label:before {
        content:'';
        position: absolute;
        top:100%;
        left:0;
        height: 2px;
        background:#ffffff;
        transition:0.3s width;
        transform-origin: left center;
    }

    .form_label:after {
        width: 100%;
        opacity: 0.4;
    }

    .form_label:before {
        width: 0;
    }

    .form_input {
        width: 100%;

        padding: 0.5rem;

        border:0;

        background: transparent;
        color:white;
    }

    .form_input:active, .form_input:focus {
        outline: none;
        border-bottom-color: white;
    }

    .form_label:focus-within .form_label-text {
        transform: translateY(-70%) scale(0.7);
    }

    .form_label:focus-within:before{
        width: 100%;
    }

    .form_submit {
        cursor: pointer;
        align-self: start;
        margin-top: 1rem;
        padding: 0.5rem 2rem;
        border:0;
        font-size: 0.8rem;
        background: white;
        box-shadow: 5px 5px 21px 9px rgba(0, 0, 0, 0.34);
        transition: all 0.2s ease-out;
    }

    .form_submit:hover, .form_submit:focus {
        background-color: #181818;
        color:white;
        transform: scale(1.1);
    }
</style>