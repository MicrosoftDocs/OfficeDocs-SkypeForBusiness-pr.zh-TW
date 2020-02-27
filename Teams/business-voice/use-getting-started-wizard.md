---
title: 使用 [快速入門精靈] 設定商務語音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba381659572fa8cfda6ac605a2910ef19220dcbd
ms.sourcegitcommit: 29034bda30a8460eb18600785f785528d0944041
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2020
ms.locfileid: "42285815"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>使用 [快速入門精靈] 設定商務語音

Microsoft 365 商務語音快速入門精靈可讓您在 Microsoft Teams 中快速設定，以撥打及接聽電話。 如果您是剛起步的小型企業，精靈可在幾分鐘內幫助您啟動並運作電話號碼、通話功能表、問候以及更多。 如果您是已建立電話語音解決方案的較大型企業，精靈可幫助您設定試驗，因此在推行到所有人之前，可先讓少數使用者嘗試商務語音。 無論是哪一種方式，精靈完成後，您就可以開始使用商務語音！

建議您在開始使用精靈之前，先閱讀本文。 當您準備好執行精靈時，請在[開始使用 Microsoft 365 商務語音](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice)頁面選取 **[開始使用]**。 請使用建立訂閱所用的帳戶登入，或其他全域系統管理員的帳戶登入。

> [!IMPORTANT]
> 目前在加拿大和英國都有提供商務語音。 2020 年開始將有更多國家/地區可使用。
>
> 只有當您的使用者信箱位於 Microsoft 365 中時，才能使用 Microsoft Teams 和商務語音。  不支援內部部署 Exchange Server 上的信箱。

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

如果不想立即自訂任何內容，就大功告成了！ 您可以立即開始使用商務語音。

## <a name="emergency-services-location"></a>緊急服務位置

<table>
    <tr>
        <td>如果需要變更緊急地址，請按一下 <b>[編輯]</b>，然後輸入新地址。 您提供的地址需經過驗證，以確認其合法性且格式正確，可供緊急回應服務時使用。 然後，此地址會指派給在下一個步驟中指派號碼的所有使用者。 如果您有位於超過單一位置的員工，請參閱<a href="./customize-business-voice.md">商務語音設計自訂</a>，了解如何在準備 [快速入門精靈] 後，新增並指派更多緊急地址。</td> 
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400"></td></tr>
</table>

如需詳細資訊，請參閱[什麼是緊急位置、地址和通話路由](../what-are-emergency-locations-addresses-and-call-routing.md) (英文版)？

## <a name="company-phone-number"></a>公司電話號碼

<table>
    <tr>
        <td>除了新的當地電話號碼以外，您還可以購買免付費電話號碼，或將現有的號碼移轉到 Microsoft 365。 若要設定免付費電話號碼，您必須購買通話方案。 若要將一或多個號碼移轉至 Microsoft 365，請在精靈完成後，前往 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心</a>。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 如果您將現有的電話號碼移轉到 Microsoft 365，您仍會在精靈中看到臨時的電話號碼。 這是預期行為 。 完成精靈及移轉程序後，預先存在的號碼將取代臨時電話號碼。

## <a name="user-licenses"></a>[使用者授權]

<table>
    <tr>
        <td>若要指派使用者授權，請選取組織中需要撥打或接聽 Teams 外部電話 (例如與供應商通話) 的人員。 您只能指派可用的商務語音授權數量。 如果需要更多，您可以在精靈完成後購買額外的授權。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 在精靈完成後，您可以將現有的電話號碼移轉到 Microsoft 365。 完成移轉程序後，已移轉的電話號碼將取代由精靈提供的臨時電話號碼。

## <a name="incoming-call-greeting"></a>來電問候語

<table>
    <tr>
        <td>您可以上傳最多 5 Mb 的音效檔 (MP3 或 WAV) 做為來電問候語，或可以輸入您的問候語，而 Microsoft 365 會使用 [文字轉換語音] 功能將其讀給來電者。 當來電者撥打貴公司的電話號碼時，來電者首先聽到的即是該問候語。 若為文字轉換語音，您可能需要使用拼音來正確發音。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>通話功能表和來電轉接

<table>
    <tr>
        <td>您可以將所有來電轉接給特定使用者，或設定來電者可選擇的功能表選項。 如果建立通話功能表，您可以指定來電者透過語音或在電話鍵盤上按數字來選取選項。 每個功能表選項皆可將通話轉接給特定使用者。<br><br>
        您可以上傳最多 5MB 的音效檔 (MP3 或 WAV) 以提供來電者指示，或者直接輸入指示。 Microsoft 365 會使用 [文字轉換語音] 將指示讀給來電者。 您可能需要按照發音拼音字詞，以獲得正確發音。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> [快速入門精靈] 可協助您設定簡單的通話功能表，讓您快速上手。 如果要設定通話功能表中的多個電話號碼，或者要設定更複雜的通話功能表 (也稱為自動語音應答)，您可以在結束精靈後，參閱[設定雲端自動語音應答](set-up-auto-attendants.md)。

<table>
    <tr>
        <td> <p>[快速入門精靈] 會使用您輸入的資訊來設定商務語音。 您可以在<b>概觀</b>頁面看到指派給使用者的電話號碼、查看通話功能表，聆聽問候語等。</p>
             <p>設定需要數分鐘的時間。 若您選取 <b>[完成]</b>，我們會繼續在背景中設定商務語音。 您也可以等待設定完成。 完成之後，請移至 <a href="https://admin.teams.microsoft.com" target="_blank">[Teams 系統管理中心]</a> 的 <b>[語音]</b>，以設定更多商務語音功能。</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>
