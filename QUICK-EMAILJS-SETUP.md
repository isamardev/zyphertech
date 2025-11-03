# Quick EmailJS Setup Guide - For samarahmad6030@gmail.com
## 5 Minutes Setup - Get Emails from Contact Form

---

## 🚀 Quick Steps (Follow Exactly)

### Step 1: Create EmailJS Account (2 min)

1. Open: **https://www.emailjs.com/**
2. Click **"Sign Up"**
3. Choose **"Sign up with Google"**
4. Login with **samarahmad6030@gmail.com**
5. Done! ✅

---

### Step 2: Connect Gmail (1 min)

1. In EmailJS dashboard, click **"Email Services"**
2. Click **"Add New Service"**
3. Select **"Gmail"**
4. Click **"Connect Account"**
5. Login with **samarahmad6030@gmail.com**
6. Click **"Allow"** for permissions
7. **IMPORTANT:** Copy your **Service ID** 
   - It looks like: `service_abc1234`
   - Write it down! 📝

---

### Step 3: Create Email Template (2 min)

1. Click **"Email Templates"**
2. Click **"Create New Template"**
3. Fill in:

**Template Name:**
```
ZypherTech Contact Form
```

**To Email:** (Where you want to receive emails)
```
samarahmad6030@gmail.com
```

**From Name:**
```
{{from_name}}
```

**Subject:**
```
New Contact Form - {{from_name}}
```

**Content (Copy-Paste This):**
```
Name: {{from_name}}
Email: {{from_email}}
Phone: {{phone}}
Service: {{service}}

Message:
{{message}}

---
Sent from ZypherTech Contact Form
```

4. Click **"Save"**
5. **IMPORTANT:** Copy your **Template ID**
   - It looks like: `template_xyz5678`
   - Write it down! 📝

---

### Step 4: Get Public Key (30 seconds)

1. Click your profile icon (top right)
2. Click **"Account"**
3. Go to **"General"** tab
4. Find **"Public Key"**
5. **IMPORTANT:** Copy your **Public Key**
   - It looks like: `aBc123XyZ456`
   - Write it down! 📝

---

### Step 5: Update Your Code (1 min)

Open **`script.js`** file in your code editor.

**Find Line 178:**
```javascript
emailjs.init("YOUR_PUBLIC_KEY");
```

**Replace with YOUR Public Key:**
```javascript
emailjs.init("aBc123XyZ456");  // Paste your actual public key here
```

**Find Line 213:**
```javascript
emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', form)
```

**Replace with YOUR IDs:**
```javascript
emailjs.sendForm('service_abc1234', 'template_xyz5678', form)
// Replace service_abc1234 with your Service ID
// Replace template_xyz5678 with your Template ID
```

**Save the file!** 💾

---

## ✅ Test Your Setup

1. Open your website
2. Go to **Contact** section
3. Fill the form:
   ```
   Name: Test User
   Email: test@email.com
   Phone: +1 555 1234
   Service: Digital Marketing
   Message: This is a test
   ```
4. Click **"Send Message"**
5. Check **samarahmad6030@gmail.com** inbox! 📧
6. Email should arrive in 2-3 seconds!

---

## 📋 Your Configuration Summary

Fill this as you setup:

```
✅ EmailJS Account: samarahmad6030@gmail.com

Step 2 - Service ID:
Service ID: _____________________

Step 3 - Template ID:
Template ID: _____________________

Step 4 - Public Key:
Public Key: _____________________

✅ Updated script.js with above IDs
✅ Tested and working!
```

---

## 🎯 Example (What Your script.js Should Look Like)

After you update, your code should look like this:

```javascript
// Line 178
emailjs.init("dFg789HiJ012KlM");  // Your actual public key

// Line 213
emailjs.sendForm('service_xyz9876', 'template_abc5432', form)
// Your actual Service ID and Template ID
```

---

## 🐛 If Something Goes Wrong

### Problem: No email received

**Check:**
1. Open browser console (Press F12)
2. Look for errors
3. Make sure all 3 IDs are correct:
   - Public Key in line 178
   - Service ID in line 213
   - Template ID in line 213

**Still not working?**
- Go to EmailJS Dashboard
- Click "Logs" 
- Check if email was sent
- Check spam folder in Gmail

---

## 📧 Your Email Settings

**Receive emails at:** samarahmad6030@gmail.com  
**Displayed on website:** samarahmad6030@gmail.com  
**Backup email:** info@zyphertech.com

---

## 💡 Pro Tips

1. **Check Spam Folder:** First emails might go to spam
2. **Mark as Not Spam:** This helps future emails
3. **Create Label:** Create "Website Leads" label in Gmail
4. **Mobile Notifications:** Turn on Gmail notifications
5. **Quick Response:** Reply within 24 hours for best results

---

## 🔒 Free Tier Limits

**You get FREE:**
- ✅ 200 emails per month
- ✅ Perfect for starting out
- ✅ No credit card needed

**If you need more later:**
- Upgrade to $7/month for 1,000 emails

---

## ✨ All Set!

Once you complete these 5 steps, your contact form will send emails directly to **samarahmad6030@gmail.com** without any backend server!

**Questions?** Check the detailed guide in `EMAILJS-SETUP-GUIDE.md`

---

**Setup Time:** 5 minutes  
**Cost:** FREE  
**Emails per month:** 200  
**Your Email:** samarahmad6030@gmail.com

**Ready? Let's go!** 🚀

