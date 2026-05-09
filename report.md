# Design Evaluation Report

Project evaluated: `NEO CUIZON - PORTFOLIO`  
Reference material: `Lesson-3-Evaluation-Techniques.pdf`

## 1. Evaluation Basis

This report uses the evaluation approaches discussed in Lesson 3:

- System functionality and usability assessment
- Interface effect on the user
- Cognitive walkthrough
- Heuristic evaluation
- Review-based evaluation
- Suggested user-participation methods such as think-aloud observation, interviews, and questionnaires

The project is a static portfolio website built in `index.html`, supported by local image assets in the `images` folder.

## 2. Overall Design Impression

The portfolio has a strong brutalist visual direction. The black, white, yellow, red, and blue palette gives the site a memorable identity, and the large typography makes the landing section immediately recognizable. The page feels energetic and personal, which suits a student portfolio or tour/reflection project.

However, the design currently prioritizes visual impact more than usability. The hero section is very large, the typography is heavy across almost every section, and several interaction and content details reduce clarity. The site needs stronger hierarchy, clearer affordances, working content paths, and better accessibility support.

Overall rating: **7/10 for visual identity, 5/10 for usability, 6/10 overall.**

## 3. Strengths

### Strong visual identity

The design is consistent and recognizable. The repeated use of thick borders, high contrast blocks, uppercase labels, and primary colors creates a clear style.

### Clear main sections

The navigation structure is simple: About, Gallery, Companies, and Certification. Users can quickly understand the main areas of the site.

### Good use of contrast

Most text has strong contrast against its background. The black-on-white and yellow-on-black combinations are visually clear and readable.

### Gallery interaction adds engagement

The day-based gallery cards and modal interaction make the portfolio more interactive than a plain static page. This supports the portfolio goal of showing experiences from the tour.

## 4. Main Usability Issues

### 4.1 Visibility of system status

The gallery cards open a modal, but the cards do not clearly tell users that they are clickable. The cursor changes on hover, but there is no visible label such as "View photos" or an icon that communicates the result of clicking.

The modal also lacks keyboard-focused feedback and does not show users how many images are inside each day. This weakens visibility of the current state.

Recommendation:

- Add a clear action label to each gallery card, such as `View Photos`.
- Add visible focus states for keyboard users.
- Add a photo count or small preview image to each gallery card.

### 4.2 Match between design and user expectations

The site presents itself as a portfolio, but much of the content is generic. The hero says "IT Professional x Web Developer," while the page content mainly documents an educational tour. This creates a mismatch between the user's expectation and the actual content.

Recommendation:

- Decide whether the site is primarily a personal web developer portfolio or an educational tour portfolio.
- If it is a tour portfolio, rename key text to reflect that purpose.
- If it is a professional portfolio, add actual projects, technologies used, and links to work.

### 4.3 User control and freedom

The modal has a close button and supports closing by clicking outside the modal, which is good. However, there is no Escape key support, no visible focus trap, and no next/previous image navigation.

Recommendation:

- Allow users to close the modal with the Escape key.
- Add previous and next controls for image browsing.
- Keep keyboard focus inside the modal while it is open.

### 4.4 Consistency and standards

The brutalist style is consistent visually, but several interface details do not follow common web standards:

- Gallery cards are clickable `div` elements instead of buttons or links.
- The hamburger menu is also a `div`, not a button.
- Placeholder links are used for LinkedIn and GitHub.
- The email address is still `neo@example.com`.

Recommendation:

- Convert clickable `div` elements into semantic `button` elements.
- Replace placeholder links with real destinations or remove them.
- Use proper accessible labels for the hamburger menu and modal close button.

### 4.5 Error prevention and broken content

The certification image is broken. The HTML references:

`images/CertNINeo.jpg`

But the available file appears to be:

`images/certificate.jpg`

This causes the certification section to fail visually and reduces credibility.

Recommendation:

- Update the certificate image path to the correct file.
- Check all image paths before submission.
- Add fallback text or styling for missing images.

## 5. Cognitive Walkthrough

The cognitive walkthrough asks whether users can understand the available actions, predict the correct action, and understand the feedback after acting.

### Task: View gallery photos

Expected user goal: Open photos from one day of the tour.

Findings:

- Users can see the day cards, but the cards do not explicitly say they open photos.
- The hover movement suggests interactivity on desktop, but mobile users do not get hover feedback.
- After clicking, the modal appears, which is understandable.
- There are no next/previous controls, so users must close the modal and open another day manually.

Result: Mostly usable, but the action should be more explicit.

### Task: Contact the owner

Expected user goal: Find real contact information.

Findings:

- The Contact button scrolls to the footer, which is understandable.
- The email address is a placeholder.
- LinkedIn and GitHub links do not lead anywhere.

Result: The workflow is visually present but functionally incomplete.

### Task: Check certification

Expected user goal: View proof of completion.

Findings:

- The section title is clear.
- The certificate image is broken because of the incorrect file path.
- The fallback still shows text details, but the main proof is missing.

Result: The task fails visually and should be fixed before submission.

## 6. Visual Design Assessment

### Typography

The typography creates a strong identity, but almost all text uses the same heavy uppercase style. This makes scanning harder, especially in longer paragraphs.

Recommendation:

- Keep the heavy uppercase style for headings and labels.
- Use normal sentence case for paragraph content.
- Consider using a more readable body font while keeping the display font for headings.

### Layout and hierarchy

The hero section is memorable, but it takes almost the entire first viewport. Users see very little evidence of the actual portfolio content at first glance.

Recommendation:

- Slightly reduce the hero text size.
- Let the next section appear earlier in the first viewport.
- Add a small visual preview of gallery or project content near the hero.

### Color

The palette is bold and consistent. The yellow, red, and blue accents are effective, but the colors are intense and should be used more selectively.

Recommendation:

- Keep yellow as the main accent.
- Use red mainly for warnings, emphasis, or destructive actions.
- Use blue sparingly to avoid competing visual emphasis.

### Imagery

The project includes many relevant local images, but the landing page does not show any real photo content. For a tour-based portfolio, photos should appear earlier.

Recommendation:

- Add one strong real image or collage preview in the first screen or immediately after it.
- Use actual company or tour photos as previews for gallery cards.

## 7. Accessibility and Responsiveness

Accessibility issues:

- Clickable cards are not keyboard-accessible by default.
- The hamburger menu lacks button semantics and accessible labels.
- Modal behavior lacks Escape support and focus management.
- Repeated uppercase text reduces readability.
- The close button text `X` should have an accessible label like `Close gallery`.

Responsive issues:

- The CSS includes a breakpoint for smaller screens, which is good.
- The large hero typography may still feel cramped on mobile.
- Hover-only interaction cues are weaker on touch devices.

Recommendation:

- Use semantic HTML buttons for all interactive controls.
- Add `aria-label` values where needed.
- Add keyboard support for modal open/close behavior.
- Test the site at mobile widths and reduce hero scale if text feels crowded.

## 8. Suggested User Evaluation

Following the PDF's user-participation methods, the next step should be a short usability test.

Suggested tasks:

1. Ask a user to find the gallery photos from Day 2.
2. Ask a user to find proof of completion or certification.
3. Ask a user to contact the portfolio owner.
4. Ask a user to explain what the site is mainly about after viewing the first screen.

Suggested methods:

- Think-aloud observation: Ask users to say what they are thinking while using the site.
- Post-task walkthrough: Ask what confused them after each task.
- Short questionnaire: Ask users to rate clarity, readability, visual appeal, and ease of navigation.

Suggested questions:

- Was the purpose of the website clear?
- Which section did you notice first?
- Did you understand that the day cards were clickable?
- Was the text easy to read?
- Did the design feel professional, personal, or too intense?

## 9. Priority Fixes

High priority:

- Fix the broken certificate image path.
- Replace placeholder email, LinkedIn, and GitHub links.
- Make gallery cards and hamburger menu semantic buttons.
- Add accessible labels and keyboard support for the modal.

Medium priority:

- Reduce the hero scale slightly.
- Add real image previews to the gallery cards.
- Improve the content match between "portfolio" and "educational tour."
- Use more readable paragraph typography.

Low priority:

- Add image counts to gallery cards.
- Add next/previous controls in the modal.
- Add smoother section hierarchy and more breathing room in content areas.

## 10. Conclusion

The project has a strong and memorable visual concept. Its biggest strength is identity: it does not look generic. The main weakness is usability polish. Based on the evaluation techniques from the PDF, the site should be improved by fixing broken content, making interactions clearer, supporting keyboard and mobile users, and aligning the content more closely with the site's stated purpose.

With those improvements, the design can keep its bold brutalist personality while becoming easier to understand, navigate, and trust.
