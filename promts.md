Build a Next.js 15 application that extracts calendar event details from user-pasted text and adds them to Google Calendar, with a minimal, modern UX. The application should meet the following requirements:

1. User Interface:
   - Create a clean, minimal, centered (horizontally and vertically) layout.
   - Implement two views:
     - Input View: Visible initially, with a large Google-style textarea for pasting text (e.g., email or message) and an "Analyze" button.
     - Confirmation View: Displayed after analysis, showing extracted event details (title, date, time, location, attendees), a confirmation message (e.g., "Add 'Meeting with John' at 3 PM tomorrow to your calendar?"), and "Confirm" and "Cancel" buttons.
   - Include a "Sign in with Google" button (visible when not authenticated) and a "Sign out" button (visible when authenticated).
   - Use subtle animations (e.g., smooth transitions for view switches, buttons) for polished UX.
   - Ensure modern aesthetic with clean typography, cohesive colors, and minimal visuals.

2. Functionality:
   - In the input view, allow users to paste text and click "Analyze" after Google authentication.
   - Use Google OAuth 2.0 (via GOOGLE_CLIENT_ID, GOOGLE_CLIENT_SECRET) with next-auth for user authentication (scope: profile, email, calendar.events).
   - Use OpenAI API (via OPENAI_API_KEY) with a system prompt including the pasted text to generate a JSON object containing:
     - Event details: title, start (dateTime), location, attendees (array of names or emails).
     - Example output: { "title": "Meeting with John", "start": "2025-06-13T15:00:00", "location": "Starbucks", "attendees": ["John"] }
   - Display extracted details in the confirmation view with a prompt to add to Google Calendar.
   - Use Google Calendar API to add the event to the user's calendar upon confirmation.
   - Show success/error messages (e.g., simple alerts) after attempting to add the event.

3. Technical Requirements:
   - Use Next.js 15 with TypeScript for type safety.
   - Use Tailwind CSS v4 (search web for latest v4 setup, avoid v3 syntax) for styling, ensuring a simple, Google-like design.
   - Use next-auth for Google OAuth 2.0 to simplify authentication and token management.
   - Implement robust error handling with user-friendly messages (e.g., alerts for invalid text or API errors).
   - Optimize for performance and responsiveness across devices.
   - Use environment variables (GOOGLE_CLIENT_ID, GOOGLE_CLIENT_SECRET, OPENAI_API_KEY, NEXTAUTH_SECRET, NEXTAUTH_URL) via .env.local.
   - Use lightweight libraries for animations (e.g., Framer Motion).
   - Keep it minimal, stateless, with no database; use sessions for token storage.

4. Constraints:
   - Use gpt-4o-mini for cost-efficient OpenAI text analysis, ensuring valid JSON output.
   - Handle cases where no event details are extracted with a fallback message (e.g., "No event details found").
   - Implement all features fully; no mockups or placeholders. Clarify ambiguities via questions.

5. Deliverables:
   - A fully functional Next.js 15 application with a minimal, modern UX.
   - A clean, modular codebase with robust error handling and optimization.
   - A .env.example file template for environment variables.