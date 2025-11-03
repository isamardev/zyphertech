# EmailJS Setup Guide - Contact Form Configuration
## Free Email Integration Without Backend

**Last Updated:** November 3, 2025  
**Service:** EmailJS (Free - 200 emails/month)  
**Setup Time:** 10-15 minutes

---

## 🎯 What You'll Get

✅ **Contact form emails sent directly to your inbox**  
✅ **No backend server needed**  
✅ **No database required**  
✅ **Completely free (200 emails/month)**  
✅ **Auto-response to customers**  
✅ **Professional email notifications**

---

## 📧 Step-by-Step Setup Instructions

### Step 1: Create EmailJS Account (2 minutes)

1. Go to: **https://www.emailjs.com/**
2. Click **"Sign Up Free"**
3. Sign up using:
   - Google Account (Recommended - fastest)
   - OR Email & Password
4. Verify your email if using email signup

---

### Step 2: Add Email Service (3 minutes)

1. After login, go to **"Email Services"** in dashboard
2. Click **"Add New Service"**
3. Choose your email provider:

#### Option A: Gmail (Recommended for Personal)
   - Select **"Gmail"**
   - Click **"Connect Account"**
   - Login with your Gmail
   - Allow permissions
   - Done! ✅

#### Option B: Outlook/Hotmail
   - Select **"Outlook"**
   - Follow similar steps as Gmail

#### Option C: Custom SMTP (For Business Email)
   - Select **"SMTP"**
   - Enter your email settings:
     ```
     SMTP Server: mail.yourdomain.com
     Port: 587 (or 465 for SSL)
     Username: your@email.com
     Password: your_password
     ```

4. **Important:** Copy your **Service ID** (looks like: `service_xxxxxxx`)
   - Save it somewhere - you'll need it!

---

### Step 3: Create Email Template (5 minutes)

1. Go to **"Email Templates"** in dashboard
2. Click **"Create New Template"**
3. Use this template:

#### Template Settings:
```
Template Name: Contact Form - ZypherTech
```

#### Template Content:

**Subject Line:**
```
New Contact Form Submission - {{from_name}}
```

**Email Body (HTML):**
```html
<div style="font-family: Arial, sans-serif; max-width: 600px; margin: 0 auto; padding: 20px; background-color: #f4f4f4;">
    <div style="background-color: #0A0E1A; padding: 20px; text-align: center; border-radius: 10px 10px 0 0;">
        <h1 style="color: #00D9FF; margin: 0;">ZypherTech</h1>
        <p style="color: #ffffff; margin: 5px 0;">New Contact Form Submission</p>
    </div>
    
    <div style="background-color: #ffffff; padding: 30px; border-radius: 0 0 10px 10px;">
        <h2 style="color: #0A0E1A; border-bottom: 2px solid #00D9FF; padding-bottom: 10px;">Contact Details</h2>
        
        <p><strong>Name:</strong> {{from_name}}</p>
        <p><strong>Email:</strong> {{from_email}}</p>
        <p><strong>Phone:</strong> {{phone}}</p>
        <p><strong>Service Interested:</strong> {{service}}</p>
        
        <h3 style="color: #0A0E1A; border-bottom: 2px solid #00D9FF; padding-bottom: 10px; margin-top: 30px;">Message</h3>
        <div style="background-color: #f9f9f9; padding: 15px; border-left: 4px solid #00D9FF; border-radius: 5px;">
            <p style="white-space: pre-wrap;">{{message}}</p>
        </div>
        
        <div style="margin-top: 30px; padding-top: 20px; border-top: 1px solid #e0e0e0; text-align: center;">
            <p style="color: #666; font-size: 12px;">This email was sent from your ZypherTech contact form</p>
        </div>
    </div>
</div>
```

4. **Set "To Email":**
   - Enter **YOUR EMAIL** where you want to receive messages
   - Example: `youremail@gmail.com`

5. Click **"Save"**

6. **Important:** Copy your **Template ID** (looks like: `template_xxxxxxx`)
   - Save it!

---

### Step 4: Get Your Public Key (1 minute)

1. Go to **"Account"** → **"General"**
2. Find **"Public Key"** section
3. Copy your public key (looks like: `YOUR_PUBLIC_KEY_HERE`)
4. Save it!

---

### Step 5: Update Your Website Code (2 minutes)

Now update the website with your EmailJS credentials:

#### Open `script.js` file and find line 178:

**REPLACE THIS:**
```javascript
emailjs.init("YOUR_PUBLIC_KEY");
```

**WITH YOUR PUBLIC KEY:**
```javascript
emailjs.init("abc123XYZdefGHI456");  // Your actual public key
```

#### Then find line 213:

**REPLACE THIS:**
```javascript
emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', form)
```

**WITH YOUR IDS:**
```javascript
emailjs.sendForm('service_abc123', 'template_xyz456', form)
```
// Replace with your actual Service ID and Template ID

---

## ✅ Step 6: Test Your Contact Form

1. Save all files
2. Open your website
3. Go to Contact section
4. Fill out the form:
   ```
   Name: Test User
   Email: test@example.com
   Phone: +1 (555) 123-4567
   Service: Digital Marketing
   Message: This is a test message
   ```
5. Click **"Send Message"**
6. Wait 2-3 seconds
7. Check your email inbox! 📧

---

## 🎨 Optional: Add Auto-Reply to Users

Want to automatically reply to users who fill the form?

### Create Second Template (Auto-Reply):

1. Go to **"Email Templates"**
2. Click **"Create New Template"**
3. Name: `Auto Reply - Contact Form`

**Template Settings:**

**To Email:**
```
{{from_email}}
```

**Subject:**
```
Thank you for contacting ZypherTech!
```

**Body:**
```html
<div style="font-family: Arial, sans-serif; max-width: 600px; margin: 0 auto; padding: 20px; background-color: #f4f4f4;">
    <div style="background-color: #0A0E1A; padding: 20px; text-align: center; border-radius: 10px 10px 0 0;">
        <h1 style="color: #00D9FF; margin: 0;">ZypherTech</h1>
        <p style="color: #ffffff; margin: 5px 0;">Digital Marketing & Web Development</p>
    </div>
    
    <div style="background-color: #ffffff; padding: 30px; border-radius: 0 0 10px 10px;">
        <h2 style="color: #0A0E1A;">Hi {{from_name}}! 👋</h2>
        
        <p>Thank you for reaching out to ZypherTech!</p>
        
        <p>We've received your message regarding <strong>{{service}}</strong> and our team will get back to you within 24 hours.</p>
        
        <div style="background-color: #f0f9ff; padding: 20px; border-left: 4px solid #00D9FF; border-radius: 5px; margin: 20px 0;">
            <h3 style="color: #0A0E1A; margin-top: 0;">What Happens Next?</h3>
            <ul style="color: #333;">
                <li>Our team reviews your inquiry</li>
                <li>We'll respond within 24 hours</li>
                <li>We'll schedule a free consultation call</li>
                <li>Get a custom quote for your project</li>
            </ul>
        </div>
        
        <p>In the meantime, feel free to check out:</p>
        <ul>
            <li>Our Portfolio</li>
            <li>Client Testimonials</li>
            <li>Latest Blog Posts</li>
        </ul>
        
        <div style="text-align: center; margin: 30px 0;">
            <a href="https://zyphertech.com" style="background-color: #00D9FF; color: #0A0E1A; padding: 12px 30px; text-decoration: none; border-radius: 25px; font-weight: bold; display: inline-block;">Visit Our Website</a>
        </div>
        
        <div style="margin-top: 30px; padding-top: 20px; border-top: 1px solid #e0e0e0;">
            <p style="color: #666; font-size: 14px;">Best regards,<br><strong>The ZypherTech Team</strong></p>
            <p style="color: #666; font-size: 12px;">
                📧 info@zyphertech.com<br>
                📞 +1 (415) 123-4567<br>
                🌐 www.zyphertech.com
            </p>
        </div>
    </div>
</div>
```

4. Save Template
5. Copy the **Auto-Reply Template ID**

#### Update script.js to send auto-reply:

Find the success section in `handleFormSubmission` and add:

```javascript
.then(function(response) {
    console.log('SUCCESS!', response.status, response.text);
    
    // Send auto-reply to user
    emailjs.send('YOUR_SERVICE_ID', 'YOUR_AUTO_REPLY_TEMPLATE_ID', {
        from_name: form.from_name.value,
        from_email: form.from_email.value,
        service: form.service.value
    });
    
    // Success notification
    showNotification('Thank you! Your message has been sent successfully...', 'success');
    // ... rest of code
```

---

## 📋 Your Configuration Checklist

Fill this out as you set up:

```
✅ EmailJS Account Created
✅ Email Service Connected
   Service ID: _________________
   
✅ Email Template Created
   Template ID: _________________
   
✅ Public Key Copied
   Public Key: _________________
   
✅ script.js Updated with IDs
✅ Contact Form Tested
✅ Emails Receiving Successfully

Optional:
☐ Auto-Reply Template Created
☐ Auto-Reply Configured
```

---

## 🎯 Example Configuration

Here's what your final `script.js` should look like:

```javascript
// ========== EMAILJS INITIALIZATION ==========
(function() {
    emailjs.init("abc123XYZdefGHI456");  // Your Public Key
})();

// ... other code ...

function handleFormSubmission(form) {
    // ... loading state code ...
    
    // Send email using EmailJS
    emailjs.sendForm('service_abc123', 'template_xyz456', form)
        .then(function(response) {
            // Success!
            // ... rest of code
        });
}
```

---

## 🆓 EmailJS Free Tier Limits

**What you get FREE:**
- ✅ 200 emails per month
- ✅ 2 email services
- ✅ 2 email templates
- ✅ Basic support
- ✅ No credit card required

**If you need more:**
- **Personal Plan:** $7/month - 1,000 emails
- **Professional Plan:** $15/month - 5,000 emails
- **Business Plan:** $35/month - 20,000 emails

---

## 🔒 Security Best Practices

### 1. Protect Your Public Key
- Public key is meant to be public (it's okay to expose)
- But add domain whitelist in EmailJS dashboard
- Go to Account → Security → Allowed Domains
- Add: `yourdomain.com`

### 2. Add reCAPTCHA (Optional)
To prevent spam, add Google reCAPTCHA:
```html
<script src="https://www.google.com/recaptcha/api.js"></script>
<div class="g-recaptcha" data-sitekey="YOUR_SITE_KEY"></div>
```

### 3. Rate Limiting
EmailJS automatically limits:
- Max 10 emails per minute
- Max 200 emails per month (free tier)

---

## 🐛 Troubleshooting

### Problem: "EmailJS is not defined"
**Solution:** Make sure EmailJS script is loaded before your custom script:
```html
<!-- EmailJS must come first -->
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
<!-- Then your script -->
<script src="script.js"></script>
```

### Problem: Emails not sending
**Checklist:**
1. ✅ Check browser console for errors
2. ✅ Verify Service ID is correct
3. ✅ Verify Template ID is correct
4. ✅ Verify Public Key is correct
5. ✅ Check EmailJS dashboard → Usage logs
6. ✅ Verify email service is connected

### Problem: "Service ID not found"
**Solution:** 
- Go to EmailJS dashboard
- Check exact Service ID (copy-paste)
- Make sure email service is active

### Problem: Template variables not showing
**Solution:**
- Check input `name` attributes match template variables
- Form field: `name="from_name"`
- Template: `{{from_name}}`

---

## 📞 Your Contact Information

**Update these in your website:**

1. **Email addresses** (already updated):
   - info@zyphertech.com
   - hello@zyphertech.com

2. **Phone number** (update with YOUR actual number):
   ```
   Current: +1 (415) 123-4567
   Change to: YOUR_ACTUAL_PHONE_NUMBER
   ```

3. **Location:**
   - San Francisco Bay Area, California
   - (Update if different)

---

## ✅ Final Steps

1. **Update script.js** with your EmailJS credentials
2. **Update phone number** in index.html (3 places):
   - Contact section
   - Schema markup
   - Footer
3. **Test the contact form**
4. **Check your email**
5. **Celebrate!** 🎉

---

## 📚 Resources

- **EmailJS Dashboard:** https://dashboard.emailjs.com/
- **EmailJS Documentation:** https://www.emailjs.com/docs/
- **Support:** https://www.emailjs.com/docs/support/
- **Video Tutorial:** https://www.youtube.com/watch?v=dgcYOm8n8ME

---

## 💡 Pro Tips

1. **Create different templates** for different services
2. **Track conversions** by adding to template:
   ```
   Service: {{service}}
   Source: Website Contact Form
   Date: {{reply_to}}
   ```
3. **Set up email notifications** on your phone
4. **Respond within 24 hours** for best conversion
5. **Keep template professional** but friendly

---

**Need Help?** 
If you face any issues, check the EmailJS dashboard logs or contact EmailJS support at help@emailjs.com

---

**Setup Complete!** ✅  
Your contact form is now ready to receive emails without any backend! 🚀

**Last Updated:** November 3, 2025  
**ZypherTech** - Digital Marketing Agency California

