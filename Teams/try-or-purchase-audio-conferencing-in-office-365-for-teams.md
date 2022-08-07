---
title: 在 Teams 版 Microsoft 365 中試用或購買音訊會議
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d080bb8c-3465-47bb-ad2b-9428f1a3fd24
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.lync.lac.CpcGettingStarted
- seo-marvel-mar2020
description: 瞭解如何嘗試或購買音訊會議 (PSTN 會議) Microsoft 365 的授權，或Office 365設定使用者可以撥入的電話會議。
ms.openlocfilehash: 861537c6c452612058d8e3ad8ae416b812d0bb32
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271438"
---
# <a name="try-or-purchase-audio-conferencing-in-microsoft-365-for-microsoft-teams"></a>在 Microsoft Teams 版 Microsoft 365 中試用或購買音訊會議

貴組織內的人員有時會需要透過電話來加入會議。 Microsoft Teams 包含音訊會議功能，僅適用于此情況！ 人員可以使用電話撥入 Microsoft Teams 會議，而不是在行動裝置或電腦上使用 Microsoft Teams 應用程式。

您只需要為計畫排程或主持會議的人員設定音訊會議。 撥入會議的會議出席者不需要指派任何授權給他們，也不需要其他設定。

如需定價資訊，請參閱[音訊會議的定價](https://www.microsoft.com/microsoft-teams/audio-conferencing?rtc=3)。

## <a name="step-1-buy-and-assign-audio-conferencing-licenses"></a>步驟 1：購買並指派音訊會議授權

您必須是 [全域系統管理員或計費系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ，才能執行這些步驟。

### <a name="to-buy-and-assign-user-audio-conferencing-licenses"></a>購買及指派使用者音訊會議授權

1. 瞭解您的國家/地區是否可使用 **音訊會議** 。 [音訊會議和通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

2. 取得 **音訊會議** 授權。 如果您想要：

   - 購買前先 **試用**：您可以註冊包含音訊會議的 Office 365 企業版 E5 免費試用版。 請[參閱 Office 365 企業版 E5 試用版]](https://portal.office.com/Signup?OfferId=101bde18-5ffb-4d79-a47b-f5b2c62525b3)。

   - **購買：** 請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

3. [將授權指派給](/microsoft-365/admin/manage/assign-licenses-to-users) 組織中即將排程或主持會議的使用者。

4. 如果您購買音訊會議附加元件授權和通訊點數授權，也請指派這些授權。 如需相關指示，請參閱 [指派 Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="to-buy-and-assign-pay-per-minute-audio-conferencing-licenses"></a>購買並指派每分鐘付費音訊會議授權

如果您是大量及授權客戶，您可以取得每分鐘付費的音訊會議授權。 如需每分鐘付費音訊會議授權的其他資訊，請參閱 [音訊會議每分鐘付費](audio-conferencing-pay-per-minute.md)。
  
1. 瞭解您的國家/地區是否可使用 **音訊會議** 。 [音訊會議和通話方案的國家/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

2. 取得 **音訊會議** 授權。 若要取得每分鐘付費授權，請連絡您的客戶代表。

3. [為貴組織設定通訊點](set-up-communications-credits-for-your-organization.md) 數。 若要設定通訊點數，請參閱 [什麼是通訊點數？](what-are-communications-credits.md)

    > [!IMPORTANT]
    > 如果尚未設定通訊點數，則任何擁有每分鐘付費授權的使用者都無法使用音訊會議。

4. [將授權指派給](/microsoft-365/admin/manage/assign-licenses-to-users) 組織中即將排程或主持會議的使用者。

    > [!NOTE]
    > 如果您有每分鐘付費的音訊會議授權，您也必須個別指派通訊點數授權給每個使用者。

## <a name="step-2-set-the-audio-conferencing-provider-for-people-who-lead-or-schedule-meetings"></a>步驟 2：為主持或排程會議的人員設定音訊會議提供者

當您將 **音訊會議** 授權指派給組織中沒有商務用 Skype與協力廠商音訊會議提供者整合的人員時，他們全都已設定完成並準備就緒！  (您不需要設定音訊會議提供者。) 

如果您已啟用具有協力廠商音訊會議提供者的使用者，您必須將這些使用者的提供者變更為 Microsoft。 若要變更使用者的提供者，請參閱 [指派 Microsoft 作為音訊會議提供者](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

## <a name="step-3-other-admin-tasks"></a>步驟 3：其他系統管理工作

下列步驟為 **選用**，但許多系統管理員會喜歡執行下列步驟：

1. [自訂會議邀請](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。 為使用者設定的撥入號碼會自動新增至傳送給出席者的會議邀請。 不過，您可以新增自己的說明與法律連結、文字簡訊，以及小型公司圖形。

2. [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。 這是會顯示在使用者所排程之會議中的電話號碼。

3. [設定音訊會議的自動語音應答語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) ，音訊會議自動語音應答在撥入音訊會議電話號碼時，會用來問候來電者。 只有在您使用 Microsoft 做為音訊會議提供者時，才適用此步驟。

4. [設定音訊會議 PIN 的長度](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)。

> [!NOTE]
> 使用中國 21Vianet 營運Office 365的客戶目前還無法使用此功能。 若要深入瞭解，請參閱[瞭解由 21Vianet 營運Office 365](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)。

## <a name="related-topics"></a>相關主題

[啟用組織中的 Teams](office-365-set-up.md)

[音訊會議的電話號碼](phone-numbers-for-audio-conferencing-in-teams.md)

[設定線上會議和電話會議的選項](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
