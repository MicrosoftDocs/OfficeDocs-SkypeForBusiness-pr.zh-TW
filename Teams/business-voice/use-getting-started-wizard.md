---
title: 使用 [快速入門精靈] 設定商務語音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46f6f75ce0ac14193a4f7a8cfccadf8312f92a98
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972194"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>使用 [快速入門精靈] 設定商務語音

Microsoft 365 商務語音的 [快速入門精靈] 提供您簡易且快速的方法來開始接收並撥打 Microsoft Teams 中的通話。 如果您是剛起步的小型企業，精靈可在幾分鐘內幫助您啟動並運作電話號碼、通話功能表、問候以及更多。 如果您是已具有建立好之電話語音解決方案的較大型企業，精靈可幫助您設定商務語音試驗。您可以在為所有人設定使用之前，先與少數使用者進行測試。 無論是哪一種方式，精靈完成後，您就可以開始使用商務語音！

建議您在開始使用精靈之前，先閱讀本文。 準備好時，您可以從 [[Microsoft 365 系統管理中心]](https://admin.microsoft.com/AdminPortal/Home#/homepage)開啟精靈。 請確認您已使用建立訂閱所用的帳戶登入，或其他全域系統管理員的帳戶登入。

> [!IMPORTANT]
> 目前在加拿大和英國都有提供商務語音。 2020 開始將有更多國家/地區提供。
>
> 只有當您的使用者信箱位於 Microsoft 365 之中時，才能使用 Microsoft Teams 和商務語音。  我們不支援內部部署 Exchange Server 上的信箱。

<!-- After you've finished the wizard, here are a couple articles you can check out to see what you can do with Business Voice and learn how to customize it. If you don't want to customize anything, you're done! You can start using Business Voice right away.

* [Things to try with Business Voice](things-to-try.md)
* [Customize Business Voice](customize-business-voice.md)
-->

## <a name="emergency-services-location"></a>緊急服務位置

<table>
    <tr>
        <td>如果您想變更緊急地址，請按一下 <b>[編輯]</b> 並輸入新地址。 您提供的地址需經過驗證，以確認其合法性且格式正確，可供緊急回應服務時使用。 經認證有效，則會將地址指派給在下一個步驟中指派號碼的所有使用者。 如果您有位於超過單一地點的的員工們，[自訂商務語音] 主題將會示範如何在完成 [快速入門精靈] 後，新增並指派更多的緊急地址。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

如果想要深入了解，請參閱[什麼是緊急位置、地址和通話路由](../what-are-emergency-locations-addresses-and-call-routing.md) (英文版)？

## <a name="company-phone-number"></a>公司電話號碼

<table>
    <tr>
        <td>除了設定新的當地電話號碼以外，您還可以選擇購買免付費電話號碼，或將現有的號碼移轉到 Microsoft 365。 如果您選擇設定免付費電話號碼，就必須購買通話方案。 如果您要移轉號碼到 Microsoft 365，您可以在精靈完成之後，於 [[Teams 系統管理中心]](https://admin.teams.microsoft.com) 選擇進行此動作。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 如果您選擇將現有的電話號碼移轉到 Microsoft 365，您仍會在精靈中看到臨時的電話號碼。 這樣是正常的。 完成精靈及移轉程序後，您的電話號碼將取代臨時電話號碼。

## <a name="assigning-licenses-to-users"></a>將授權指派給使用者

<table>
    <tr>
        <td>選取組織中要撥打或接聽電話的 Teams 小組以外人員 (例如與供應商通話)。 您最多可以選取您本來就可用的商務語音授權數量。 如果需要更多，您可以在精靈完成後購買額外的授權。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 如果您想要將現有的電話號碼移轉至 Microsoft 365 以供個別使用者使用，可以在精靈完成之後進行。 完成移轉程序後，已移轉的電話號碼將取代由精靈選取的臨時電話號碼。

## <a name="incoming-call-greeting"></a>來電問候語

<table>
    <tr>
        <td>您可以上傳最多 5 Mb 的音效檔 (MP3 或 WAV) 做為問候語，或可以輸入您的問候語，而 Microsoft 365 會使用 [文字轉換語音] 功能將其讀給來電者。 當來電者撥打電話公司的電話號碼時，來電者首先聽到的即是該問候語。 您可能需要拼錯字詞，或使用拼音來正確發音。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>通話功能表和來電轉接

<table>
    <tr>
        <td>您可以將所有來電轉接給特定使用者，或設定來電者可選取的通話功能表選項。 如果建立了通話功能表，您可以指定來電者在電話鍵盤上按數字，或透過語音命令說出來選取的選項。 每個功能表選項皆可轉接給一位使用者。 <br>
您可以選擇是否要上傳最多 5MB 以提供來電者指示的音效檔 (MP3 或 WAV)，或者直接輸入指示。 Microsoft 365 會使用 [文字轉換語音] 將指示讀給來電者。 您可能需要按照發音拼音字詞，以獲得正確發音。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

<table>
    <tr>
        <td> <p><b>[概觀]</b> 頁面上的 [快速入門精靈] 會處理您輸入的每件事項，並為您設定商務語音。 您可以看到指派給使用者的電話號碼、查看通話功能表，聆聽問候語以及更多。 </p>
             <p>設定商務語音只需要幾分鐘的時間。 您可以按一下 <b>[完成]</b>，我們會繼續在背景中設定商務語音，或可以等到完成後再執行。 完成之後，請移至 <a href="https://admin.teams.microsoft.com" target="_blank">[Teams 系統管理中心]</a> 的 <b>[語音]</b>，以設定更多商務語音功能。</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>