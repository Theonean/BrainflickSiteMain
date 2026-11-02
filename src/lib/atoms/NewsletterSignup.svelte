<script lang="ts">
    let status: 'idle' | 'sending' | 'done' | 'error' = $state('idle');

    async function subscribe(event: SubmitEvent) {
        event.preventDefault();
        const form = event.currentTarget as HTMLFormElement;
        status = 'sending';
        try {
            // no-cors, because the mail server doesn't allow reading its reply. So this only catches network failures, not rejected signups
            await fetch(form.action, { method: 'POST', mode: 'no-cors', body: new FormData(form, event.submitter) });
            status = 'done';
        } catch {
            status = 'error';
        }
    }
</script>

<section id="newsletter">
    <h2>Want to stay up to date?</h2>
    {#if status === 'done'}
    <p role="status">Thanks for signing up!</p>
    {:else}
    <form action="https://mail.brainflick.ch/subscribe" method="POST" accept-charset="utf-8" onsubmit={subscribe}>
        <label for="name" class="visually-hidden">Name</label>
        <input type="text" name="name" id="name" placeholder="Your name" autocomplete="name" />
        <label for="email" class="visually-hidden">Email address</label>
        <input type="email" name="email" id="email" required placeholder="Your email address" autocomplete="email" />
        <!-- honeypot for spam bots, must stay hidden and empty -->
        <div style="display:none;">
            <label for="hp">HP</label>
            <input type="text" name="hp" id="hp" />
        </div>
        <input type="hidden" name="list" value="gV892L4XFu73ry88929H1SbEww" />
        <input type="hidden" name="subform" value="yes" />
        <input type="submit" name="submit" id="submit" value={status === 'sending' ? 'Joining…' : 'Join the newsletter'} disabled={status === 'sending'} />
    </form>
    {#if status === 'error'}
    <p role="alert">Something went wrong. Please try again.</p>
    {/if}
    {/if}
</section>

<style lang="scss">
    section {
        width: 100%;
        padding: 2.5rem 0;
        text-align: center;
    }

    h2 {
        margin: 0 0 1rem;
    }

    p {
        margin: 1rem auto 0;
        line-height: 1.6;
    }

    input:focus-visible {
        outline: 0px solid currentColor;
        outline-offset: 4px;
    }

    /* no boxes, underline-only inputs */
    form {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        gap: 1rem;
    }

    input {
        flex: 1 1 12rem;
        min-width: 0;
        padding: 0.4rem 0;
        font: inherit;
        color: inherit;
        background: none;
        border: none;
        border-bottom: 2px solid currentColor;
        border-radius: 0;
    }

    input::placeholder {
        color: inherit;
        opacity: 0.6;
    }

    input[type="submit"] {
        flex: 0 0 auto;
        padding: 0.6rem 1.25rem;
        font-weight: 700;
        border: none;
        background-color: $orange;
        border-radius: 8px;
        color: white;
        text-decoration: none;
        text-underline-offset: 0.2em;
        cursor: pointer;
        transition: background-color 0.2s, color 0.2s;
    }

    // also on keyboard focus, since the focus outline above is off
    input[type="submit"]:hover:not(:disabled),
    input[type="submit"]:focus-visible {
        background-color: white;
        color: $orange;
    }

    input[type="submit"]:disabled {
        opacity: 0.6;
        cursor: wait;
    }

    .visually-hidden {
        position: absolute;
        width: 1px;
        height: 1px;
        overflow: hidden;
        clip: rect(0 0 0 0);
        white-space: nowrap;
    }
</style>
