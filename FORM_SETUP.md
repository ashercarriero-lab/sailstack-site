# Consultation Form Setup Instructions

The Sailstack Consulting website now includes an in-site consultation scheduling form that sends email notifications when someone schedules a consultation.

## Email Service: Web3Forms

The form uses **Web3Forms**, a free email service for static websites that requires no backend server.

### Setup Instructions

1. **Get Your Access Key**
   - Go to [https://web3forms.com](https://web3forms.com)
   - Enter your email address: `sailstackconsulting@gmail.com`
   - Click "Create Access Key"
   - You'll receive an access key via email

2. **Update the Website**
   - Open `index.html`
   - Find line 542: `<input type="hidden" name="access_key" value="YOUR_WEB3FORMS_ACCESS_KEY">`
   - Replace `YOUR_WEB3FORMS_ACCESS_KEY` with the actual access key you received
   - Example: `<input type="hidden" name="access_key" value="a1b2c3d4-e5f6-7890-abcd-ef1234567890">`

3. **Save and Deploy**
   - Save the file
   - Commit and push your changes
   - Deploy to your hosting service

### How It Works

When someone fills out the consultation form:

1. They enter their information:
   - Full Name
   - Email Address
   - Phone Number
   - Preferred Date & Time
   - Message/Details about their needs

2. Form is submitted to Web3Forms API

3. You receive an email at `sailstackconsulting@gmail.com` with all the details

4. The visitor sees a success message on the website

### Email Format

You'll receive emails with the subject line:
**"New Consultation Request - Sailstack Consulting"**

The email will contain all form fields:
- Name
- Email
- Phone
- Preferred Date
- Preferred Time
- Message

### Features Included

✅ **Form Validation** - All required fields must be filled out
✅ **Brand Styling** - Form matches Sailstack brand colors (magenta, purple, blue)
✅ **Success/Error Messages** - Clear feedback for users
✅ **Loading State** - Shows spinner while submitting
✅ **Date Validation** - Can't select past dates
✅ **Mobile Responsive** - Works perfectly on all devices
✅ **Smooth Animations** - Professional user experience

### Troubleshooting

**Form not sending emails?**
- Verify you've added the correct access key in index.html
- Check your spam folder
- Verify the email address in Web3Forms matches sailstackconsulting@gmail.com

**Access key expired?**
- Web3Forms access keys don't expire, but you can regenerate a new one if needed

### Testing the Form

Before going live, test the form by:
1. Open the website
2. Click "Schedule Consultation"
3. Fill out the form with test data
4. Submit
5. Check sailstackconsulting@gmail.com for the notification email

### Alternative: Use Your Own Email Service

If you prefer a different email service, you can replace Web3Forms with:
- **Formspree** - Similar to Web3Forms
- **EmailJS** - Client-side email sending
- **Custom Backend** - Build your own email API

To switch services, modify the form submission handler in the JavaScript section (lines 708-752 in index.html).

---

**Need Help?**

If you have any issues setting up the form, you can:
- Contact Web3Forms support at https://web3forms.com/support
- Keep the current setup and manually update the access key later
- Temporarily revert to the Google Form if needed
