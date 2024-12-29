---

layout: default

---

# **Moj ZET** Mobile App – Ticket Purchase Guide (QR & NFC)

> **Looking for the Croatian version?**
> [Kliknite ovdje za hrvatski jezik](index_hr.md)

## Disclaimer

> Myself and this project are **not** affiliated with Zagrebački električni tramvaj d.o.o. (ZET). The content below is shared solely for **educational and informational purposes** and reflects the system's behaviour as observed at the time of writing. I do **not** guarantee that this method is officially approved or that it will work indefinitely. By using these instructions, you agree to assume all responsibility for your actions, including compliance with ZET's Terms & Conditions and local transport regulations.
> The app's T&Cs can be found [here](https://moj.zet.hr/Account/About){:target="_blank" rel="noopener"}.

## Table of Contents

- [Moj ZET Mobile App – Ticket Purchase Guide (QR & NFC)](#moj-zet-mobile-app--ticket-purchase-guide-qr--nfc)
  - [Disclaimer](#disclaimer)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
    - [Goal](#goal)
    - [Scope](#scope)
  - [Important Disclaimers](#important-disclaimers)
  - [How It Works](#how-it-works)
    - [About The Stickers](#about-the-stickers)
      - [QR Codes](#qr-codes)
      - [NFC Tags (NTAG213)](#nfc-tags-ntag213)
  - [Step-by-Step: Generating Your Own QR Codes or NFC Tags](#step-by-step-generating-your-own-qr-codes-or-nfc-tags)
    - [Creating a QR Code](#creating-a-qr-code)
    - [Writing to an NTAG213 Tag](#writing-to-an-ntag213-tag)
  - [Example Files](#example-files)
  - [Zone and Funicular Selection](#zone-and-funicular-selection)
  - [Usage & Validation Notes](#usage--validation-notes)
  - [Additional Technical Details](#additional-technical-details)
  - [Encouraging Proper Use](#encouraging-proper-use)
  - [Future Changes / Updates](#future-changes--updates)
  - [Additional Resources](#additional-resources)
    - [ZetLoc](#zetloc)
    - [ZET info](#zet-info)
      - [GTFS Realtime Feed Disclaimer](#gtfs-realtime-feed-disclaimer)
  - [License](#license)
  - [Contact / Issues](#contact--issues)
  - [Disclaimer (Reiterated)](#disclaimer-reiterated)

## Overview

With the **Moj ZET** mobile app, you can quickly purchase a ticket by scanning an official sticker (containing QR codes or NFC tags) representing the vehicle number (e.g., `T22130`).\
However, passengers may find it inconvenient to physically scan the stickers placed inside ZET vehicles due to their awkward locations — especially when it's crowded.

### Goal

Enable people to generate and carry **their own** scannable QR or NFC tag in advance to speed up ticket purchasing.

### Scope

This guide explains how to create a personal QR code or blank NFC tag that the app recognises the same way it would an official sticker. You can then keep it in your wallet, on your keychain, or on a personally written NTAG213 sticker or an NTAG213 keychain.

For official app installation and usage instructions, see [this guide](https://www.zet.hr/cijene-prodaja-i-placanje/aplikacija-mojzet/8098){:target="_blank" rel="noopener"}.

---

## Important Disclaimers

1. **No Official Affiliation**: I am an independent public transport enthusiast with **no** endorsement from ZET.
2. **Educational Purposes Only**: This information demonstrates how one might create a personal QR/NFC code purely for convenience.
3. **Use at Your Own Risk**: I cannot be held liable if ZET discontinues or changes the format, or if your usage violates any rules.
4. **No Guarantee of Acceptance**: ZET may change its policy or system without notice. What works today may not work tomorrow.
5. **Not a Fare Evasion Tool**: This guide is **not** intended to help anyone ride for free or only buy tickets when inspectors appear. You are responsible for purchasing valid tickets **before** or upon boarding, in accordance with existing transport rules.

---

## How It Works

The **Moj ZET** app typically identifies the vehicle you're on by scanning a sticker containing information like:

- **Trams**: `T<VEHICLE_GARAGE_NUMBER>` (e.g., `T22130` for a tram numbered 22130)
- **Buses**: `B<VEHICLE_GARAGE_NUMBER>` (e.g., `B375` for a bus numbered 375)

*Vehicles bearing the aforementioned garage numbers:*\
![Vehicles bearing the aforementioned garage numbers](images/230529_Moj_ZET_resized_1.jpeg)\
*Source: City of Zagreb via [www.zagreb.hr](https://www.zagreb.hr/en/predstavljena-aplikacija-moj-zet-za-digitalnu-kupn/188168){:target="_blank" rel="noopener"}*

### About The Stickers

*Example sticker in a tram:*\
![Example sticker in a tram](images/230529_Moj_ZET_resized_4.jpeg)\
*Source: City of Zagreb via [www.zagreb.hr](https://www.zagreb.hr/en/predstavljena-aplikacija-moj-zet-za-digitalnu-kupn/188168){:target="_blank" rel="noopener"}*

#### QR Codes

- The **official** onboard QR code is a simple string like `T22130` or `B375`.
- When scanned, the app believes you're on that vehicle.

#### NFC Tags (NTAG213)

- Official ZET NFC stickers contain the same `T22130` text (or whichever the garage number is), along with some minor metadata used by the app.
- They use the **NDEF** format on an **NTAG213** chip.
- The NFC tag, while slightly hidden on the front of the sticker, can be clearly seen when viewing the sticker from the back:\
![NTAG213 tag example](images/moj-ZET-QR-karta-tramvaj-Zagreb-2.jpeg)\
*Source: Portofon.com via [www.portofon.com](https://www.portofon.com/savjeti/kako-se-koristi-aplikacija-moj-zet){:target="_blank" rel="noopener"}*

---

## Step-by-Step: Generating Your Own QR Codes or NFC Tags

### Creating a QR Code

1. **Choose a QR Generation Method**
   - For instance, use [Project Nayuki's QR Code generator library](https://www.nayuki.io/page/qr-code-generator-library){:target="_blank" rel="noopener"} or another online generator.
2. **Enter the Text**
   - For example, `T22130` (tram #22130) or `B375` (bus #375).
     - Adjust for your preferred or most-frequent vehicle. It doesn't really matter, as long as the vehicle exists.
   - **Note:** I have yet to confirm whether *any* number works or if it must exist in the app's vehicle database.
3. **Print**
   - Print a small sticker or label (on sticker paper, or as a small laminated card) containing the QR code and attach it to a commonly used personal item.
   - You **cannot** import a locally saved QR code *directly* into the **Moj ZET** app, so having a physical code on a wallet/keychain is most convenient.

### Writing to an NTAG213 Tag

1. **Obtain a Blank NTAG213 NFC tag**
   - These are widely available (e.g., [AliExpress](https://www.aliexpress.com/wholesale?SearchText=ntag213){:target="_blank" rel="noopener"}), often at low cost.
   - Ensure your phone supports NFC writing. iPhones can write to NTAG213 but may have some limitations depending on iOS version or if an older (I believe, pre-iPhone 7+) device is used.
   - Besides NFC stickers, NTAG213 NFC keychains can be used as well.
2. **Install an NFC Writing App**
   - For example, [NFC Tools](https://www.wakdev.com/en/apps/nfc-tools-android.html){:target="_blank" rel="noopener"} (available on both Android & iOS).
     - [Android](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc)
     - [iPhone](https://apps.apple.com/hr/app/nfc-tools/id1252962749)
   - Alternatively, [NXP TagWriter](https://play.google.com/store/apps/details?id=com.nxp.nfc.tagwriter) is a popular choice on Android.
3. **Create a Text Record**
   - Write a text record (NDEF) with your chosen vehicle number, e.g. `T22130` or `B375`.

---

## Example Files

In the [`examples/`](examples) folder, you'll find:

1. **`qr-example-T9999.png`** – a *sample* QR code encoding the text `T9999`.\
![Sample QR code encoding text `T9999`](examples/qr-example-T9999.png)
   - This is purely for demonstration.
   - **Not** an actual ZET vehicle number (hopefully).
2. **`ntag213-dump-sample.bin`** – a *sample* NFC NDEF dump containing the text `T9999`, along with the mentioned metadata. (To be added soon.)
   - Also for demonstration only.
   - May or may not work with the **Moj ZET** app, depending on future updates.

> **Disclaimer**: These example files are shared solely to illustrate how the data might look or be structured. They **do not** represent an official ZET tag or code and may not be recognised by **Moj ZET**. Use at your own risk, and always follow ZET's Terms & Conditions.

---

## Zone and Funicular Selection

In the **Moj ZET** app, before scanning or detecting a code/tag, you can select:

- **Zone 1**, **Zone 2**, or the **Zagreb Funicular**, along with ticket durations for each zone.
  - A combined **Karta II zone - 180 minuta** option is also available, allowing travel in both zones.
- **Funicular** tickets can also be purchased via the same process (choose "*Uspinjača*" instead of a zone).
  - The funicular tickets (sometimes labelled as **Zone 4** in the app) are strictly **one-way** (up or down single tickets).
- GPS is optional — if disabled, the app will ask you to manually select your zone.

---

## Usage & Validation Notes

- **Ticket inspectors** generally just check for an **active ticket**. They do **not** compare your vehicle number to the actual vehicle, as this would be cumbersome.
  - A ticket is valid as long as it's for the correct zone and with enough remaining time at the moment of inspection.
- **Current Observations** suggest that the system does **not** strictly verify the scanned code against the actual vehicle number, due to potential syncing/technical issues with onboard ATRON computers or route changes.
  - More details on the ATRON system can be found [here](https://mreza.bug.hr/promo/atron-ov-kontrolni-centar-24236){:target="_blank" rel="noopener"}.
- **GPS/Location**: If enabled, the app may use your phone's location to suggest a zone, but you can always set it manually.

---

## Additional Technical Details

- **NTAG213** is a Type 2 NFC tag with about **144 bytes** of usable memory for NDEF data.
  - That enables it to store 132 characters in URI (or URL) format or 130 characters in plain text format.
  - The data retention period is estimated at 10 years, with endurance rated at 100k read/write cycles.
- **NDEF (NFC Data Exchange Format)** is a standard data format for storing records (text, URIs, etc.).
- Official ZET tags typically store only a brief text record (e.g., `T22130`), but might include extra metadata blocks used by the application.
- **iPhone vs. Android**:
  - Modern iPhones (iOS 13+) can often write to NTAG213 tags through specific apps.
  - Android devices usually have fewer limitations and can read/write to most NFC Forum–compliant tags.

---

## Encouraging Proper Use

- **Buy Before or Upon Boarding**: You are responsible for having a valid ticket. Do not wait until ticket inspectors appear.
- **Respect Transit Rules**: This method is meant to avoid physically scanning the official sticker in a crowd or when a sticker is missing/obscured, **not** to cheat the system.

---

## Future Changes / Updates

ZET may:

- Enforce stricter checks on vehicle data vs. user location.
- Change the app to reject external codes.

As a daily user of the app, I'll monitor its behaviour and update this guide accordingly. If you notice that the app starts enforcing vehicle-number matching, please open [an issue](https://github.com/fscek/moj-zet-app-guide/issues){:target="_blank" rel="noopener"}.

---

## Additional Resources

### ZetLoc

This nice little third-party website from an anonymous author enables you to see real-time GPS ZET vehicle positions using the [GTFS Realtime feed data](https://www.zet.hr/odredbe/datoteke-u-gtfs-formatu/669){:target="_blank" rel="noopener"} ZET provides.\
It also accepts comma-separated value inputs, such as `2,6,11`, in order to see vehicles on multiple lines at once.

[`ZetLoc` Web](https://zetloc.quest){:target="_blank" rel="noopener"}

### ZET info

*ZET info* is a well-known Android & iOS app, also using the ZET GTFS Realtime feed data. It enables you to see stations, upcoming arrivals and more. A must have when using Zagreb public transport.

[`ZET info` Web](https://zet-info.com){:target="_blank" rel="noopener"}

#### GTFS Realtime Feed Disclaimer

Due to the aforementioned issues with the ZET ATRON system, **a lot** of the buses do not have their GPS tracking activated, so these apps are sometimes less useful when using buses.

---

## License

This guide and any accompanying assets (that are **not** ZET's intellectual property) are licensed under the MIT License. This license does **not** apply to ZET's logos, official apps, or data.

---

## Contact / Issues

- **Project Inquiries**: Open a GitHub issue or pull request if you find errors or have improvements.
- **Official ZET Inquiries**: For questions about ZET policies, see the [ZET website](https://www.zet.hr){:target="_blank" rel="noopener"}.
- **Legal Notice**: If ZET requests removal or changes to content violating their terms, I will comply promptly.

---

## Disclaimer (Reiterated)

> I share these observations in good faith to help riders purchase tickets more easily. **I am not responsible** for misuse or violations of transport rules dictated by ZET. By using this guide, you acknowledge that **you alone** are responsible for complying with ZET's Terms & Conditions.
