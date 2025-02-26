---
title: iOS უსაფრთხოების პოლიტიკა
icon: material/apple-ios
---

# iOS უსაფრთხოების პოლიტიკა

*პოლიტიკის ბოლო განახლების თარიღი: 5 დეკემბერი, 2024*

## წინასწარ შესასრულებელი ნაბიჯები

- [x] [პაროლების მენეჯერი](../solutions/passwords.md)
    - ტელეფონისთვის უნიკალური, ძლიერი პაროლის შესანახად, რომელიც ამავდროულად მარტივი შესაყვანი
      იქნება.

## პოლიტიკის დაყენება

### მომზადება

უსაფრთხოების პოლიტიკა პაროლის სიმძლავრესაც არეგულირებს და იმ შემთხვევაში, თუ თქვენი პაროლი მარტივია,
მის დაყენებას ვერ შეძლებთ. ამისთვის, პროფილის ინსტალაციამდე აუცილებელია პაროლის შეცვლა.

ახალი პაროლისთვის გამოვიყენებთ კომპიუტერის მიერ შემთხვევითი წესით შერჩეულ 4 მოკლე სიტყვას, რომლის გატეხვაც პრაქტიკულად შეუძლებელი იქნება,
ხოლო მისი შეყვანა მხოლოდ 72 საათში ერთხელ მოგიწევთ.

{% include-markdown "../../includes/mobile_biometrics.md" %}

#### ახალი პაროლის შექმნა

1. დააგენერირეთ მობილურის ახალი პაროლი FOI პაროლების გენერატორით

    /// admonition | რჩევა
        type: tip

    გენერირების ღილაკს დააჭირეთ მანამ, სანამ არ მიიღებთ პაროლს, რომლის ბოლო სიტყვასაც მარტივად დაიმახსოვრებთ.
        
    ///

    [:material-key: FOI პაროლების გენერატორი](../tools/password-generator/index.md){ .md-button .md-button--primary }

2. პაროლებში სიტყვებს შორის გამოტოვებად გამოიყენეთ "სფეისი"
3. პაროლის დამახსოვრება:
    - ჩაიწერეთ პირველი სამი სიტყვა ფურცელზე
    - ბოლო სიტყვა დაიმახსოვრეთ
    - ოთხივე სიტყვის დამახსოვრების შემდეგ გაანადგურეთ ფურცელი
4. პაროლის შენახვა **Bitwarden**-ში:
    - შექმენით ახალი ჩანაწერი, დაარქვით სახელი (მაგ. **My iPhone 15 Password**)
    - შეიყვანეთ სრული პაროლი Password ველში
    - დააჭირეთ :material-content-save: Save ღილაკს


#### პაროლის შეცვლა

1. გახსენით ![Apple Settings](../assets/img/icons/apple/settings.svg){ .twemoji } **Settings**
2. გადადით **Face ID & Passcode**
3. აირჩიეთ C**hange Passcode**
4. შეიყვანეთ არსებული პაროლი
5. აირჩიეთ **Passcode Options** > **Custom Alphanumeric Code**
6. შეიყვანეთ ახალი პაროლი. სიტყვებს შორის შეიყვანეთ "სფეისი"

{% include-markdown "../../includes/password_paper_storage.md" %}


### პროფილის დაყენება


[:material-shield-lock: FOI Security Policy-ის გადმოწერა](files/apple/foi_security_policy_ios.mobileconfig){ .md-button .md-button--primary }

1. გახსენით ![iOS Files](../assets/img/logo/ios-files.svg){ .twemoji } **Files** აპლიკაცია > **Downloads** > გახსენით გადმოწერილი ფაილი: **foi_security_policy_ios.mobileconfig**
2. გახსენით ![Apple Settings](../assets/img/icons/apple/settings.svg){ .twemoji } **Settings** > ![Apple General](../assets/img/icons/apple/general.svg){ .twemoji } **General** > **VPN & Device Management**
3. აირჩიეთ **FOI Security Policy** > დააჭირეთ **Install**-ს


### Apple Watch-ის განბლოკვა

პროფილის ინსტალაციის შემდეგ, Apple Watch-ის განბლოკვა შესაძლებელი იქნება მხოლოდ iPhone-ის მეშვეობით.

ამისთვის iPhone-ზე გახსენით **Apple Watch** აპლიკაცია > **My Watch** > ჩართეთ **Unlock with iPhone**.

Apple Watch ავტომატურად განიბლოკება იმ შემთხვევაში, თუ ტელეფონი დაკავშირებულია და განბლოკილია.

საათი განბლიკილი დარჩება იქამდე, სანამ მაჯიდან არ მოიხსნით.


## გამოყენებული პარამეტრები

FOI Security Policy მოიცავს შემდეგ კონფიგურაციას და ავტომატურად გააქტიურდება.

დაყენებული პარამეტრების დათვალიერება ასევე შეგიძლიათ 
[iMazing Profile Editor](https://apps.apple.com/us/app/imazing-profile-editor/id1487860882?mt=12){:target="_blank"}-ის მეშვეობით

### DNSSettings | DNS პარამეტრები

დააინსტალირებს ორ დაშიფრულ DNS სერვერს ტელეფონზე. მათი არჩევა შეგიძლიათ [DNS](../solutions/dns.md) გვერდზე
ინსტრუქციების მიხედვით.

### პაროლი

#### allowSimple | Allow simple passcode

- [x] ჩართული

განმარტება: ვინაიდან პაროლებში სიტყვებს ვიყენებთ, სადაც განმეორებადი სიმბოლოები ნორმალურია,
მაგ: cherry, ეს შეზღუდვა აუცილებელი არაა.

#### forcePIN | Require passcode on device

- [x] ჩართული

განმარტება: ჩართულია უსაფრთხოების გაზრდის მიზნით, რათა შეუძლებელი იყოს მოწყობილობის პაროლის
დაყენების გარეშე გამოყენება.

#### maxFailedAttempts | Maximum failed attempts

- [x] 11 ცდა

განმარტება: ჩართულია უსაფრთხოების გაზრდის მიზნით, რათა პაროლის 11-ჯერ არასწორად შეყვანის შემდეგ,
მოწყობილობაში მონაცემები წაიშალოს.

#### Minimum passcode length

- [x] 15 სიმბოლო

განმარტება: დაწესებულია მინიმალური სიგრძე უსაფრთხოების გაზრდის მიზნით. 15 სიმბოლო არის 4 მარცვლის
გამოყენების შემთხვევაში, ყველაზე მცირე შესაძლო სიმბოლოების რაოდენობა (4x3 სიმბოლოიანი მარცვალი + 3 წერტილი, სფეისი ან სხვა გამოყოფა)

#### pinHistory | Passcode history

- [x] 2

განმარტება: iOS-ზე ძველი პაროლის გამოყენება 72 საათის განმავლობაში შეიძლება. შეზღუდვის ჩართვა, 
რომლითაც ახალი პაროლი ძველი ორი პაროლის სიაში არ უნდა იყოს, ამ ფუნქციას გამორთავს, მეტი უსაფრთხოებისთვის.

#### requireAlphanumeric | Require alphanumeric value

- [ ] გამორთულია

განმარტება: იმის მიუხედავად, რომ პაროლში მხოლოდ ციფრების გამოყენება არ შეიძლება, ეს პარამეტრი გათიშულია,
რადგან მისი ჩართვის შემთხვევაში, მომხმარებელს მოუწევს სიტყვებთან ან მარცვლებთან ერთად, ციფრების გამოყენებაც,
რაც არ არის საჭირო და პაროლის შეყვანას ართულებს.


### აკრძალვები

### allowApplePersonalizedAdvertising | Allow Apple Personalized Advertising

- [ ] გამორთული

განმარტება: გამორთულია პრივატულობის გაზრდის მიზნით, რათა შემცირდეს Apple-სთვის პერსონალური 
მონაცემების გადაგზავნის რისკი.

### allowAutoUnlock | Allow Apple Watch to auto unlock device

- [ ] გამორთული

განმარტება: გამორთულია უსაფრთხოების გაზრდის მიზნით, რათა ტელეფონის გახსნა Apple Watch-ით
შეუძლებელი იყოს.

#### allowCloudKeychainSync | Allow iCloud Keychain Sync

- [ ] გამორთული

განმარტება: გამორთულია უსაფრთხოების გაზრდის მიზნით, რათა შეიზღუდოს მოწყობილობაზე შენახულ 
სენსიტიურ მონაცემებზე - პაროლებსა და სხვა გასაღებებზე არასანქცირებული წვდომა.

#### allowDiagnosticSubmission | Allow submitting diagnostic and usage data to Apple

- [ ] გამორთული

განმარტება: გამორთულია უსაფრთხოების გაზრდის მიზნით, რათა შემცირდეს Apple-სთვის 
პერსონალური და სენსიტიური მონაცემების გადაგზავნის რისკი.

#### allowPasswordSharing | Allow password sharing

- [ ] გამორთული

განმარტება: გამორთულია უსაფრთხოების გაზრდის მიზნით, რათა თავიდან ავიცილოთ პაროლების 
არასანქცირებული გაზიარება.

