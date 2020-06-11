---
title: 在 Microsoft 365 for 團隊中試用或購買音訊會議
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.lync.lac.CpcGettingStarted
- seo-marvel-mar2020
description: '瞭解如何試用或購買 Microsoft 365 或 Office 365 的音訊會議（PSTN 會議）授權，以設定人員可以撥入的電話會議。 '
ms.openlocfilehash: db49a690ef0936dc22a618756d15064543074137
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691539"
---
# <a name="try-or-purchase-audio-conferencing-in-microsoft-365-for-microsoft-teams"></a>在 microsoft 365 for Microsoft 團隊中試用或購買音訊會議

貴組織內的人員有時會需要透過電話來加入會議。 Microsoft 團隊只有在這種情況下才包含音訊會議功能！ 使用者可以使用電話撥入 Microsoft 團隊會議，而不是在行動裝置或電腦上使用 Microsoft 團隊 app。

您只需要為規劃排程或領導會議的人員設定音訊會議。 在會議中呼叫會議的出席者不需要獲指派任何授權，也不需要其他設定。

如需定價資訊，請參閱[音訊會議的定價](https://products.office.com/skype-for-business/audio-conferencing#Requirements)。

## <a name="step-1-buy-and-assign-audio-conferencing-licenses"></a>步驟1：購買並指派音訊會議授權

您必須是[全域系統管理員或帳單管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)，才能執行這些步驟。

### <a name="to-buy-and-assign-user-audio-conferencing-licenses"></a>若要購買並指派使用者音訊會議授權：

1. 瞭解您的國家/地區是否提供**音訊會議**。 [音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 
    
2. 取得您的**音訊會議**授權。 如果您想要：

   - 在購買前先**試試**看：您可以註冊 Office 365 企業版 E5 免費試用版，包括音訊會議。 請參閱[Office 365 企業版 E5 試用版](https://portal.office.com/Signup?OfferId=101bde18-5ffb-4d79-a47b-f5b2c62525b3)。

   - **購買**：請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

3. 您可以[個別或大量將使用者新增](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)至組織中要排程或領導會議的人員。

4. 如果您購買的是 [音訊會議附加元件授權] 和 [通訊點數] 授權，也請指派它們。 如需相關指示，請參閱[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

### <a name="to-buy-and-assign-pay-per-minute-audio-conferencing-licenses"></a>若要購買並指派每分鐘付費的音訊會議授權：

如果您是大量和授權的客戶，您可以取得每分鐘付費的音訊會議授權。 如需每分鐘付費音訊會議授權的詳細資訊，請參閱[音訊會議每分鐘支付](audio-conferencing-pay-per-minute.md)。 
  
1. 瞭解您的國家/地區是否提供**音訊會議**。 [[國家/地區] 與 [音訊會議] 和 [通話方案] 的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 
    
2. 取得您的**音訊會議**授權。 若要取得每分鐘付費授權，請與您的帳戶代表聯繫。
    
3. 為您的組織[設定通訊點數](set-up-communications-credits-for-your-organization.md)。 若要設定通訊點數，請參閱[什麼是通訊信用？](what-are-communications-credits.md)
    
    > [!IMPORTANT]
    > 如果通訊點數尚未設定，音訊會議將無法針對每分鐘付費授權的使用者使用。

4. 您可以[個別或大量將使用者新增](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)至組織中要排程或領導會議的人員。

    > [!NOTE]
    > 如果您有音訊會議每分鐘付費的授權，您就不需要為每位使用者分別指派通訊信用額度授權，以供語音會議使用（您可能仍需要為其他服務指派）。

## <a name="step-2-set-the-audio-conferencing-provider-for-people-who-lead-or-schedule-meetings"></a>步驟2：為領導或排程會議的人員設定音訊會議提供者

當您將**音訊會議**授權指派給貴組織中沒有與協力廠商音訊會議提供者整合之商務用 Skype 的人員時，他們就全都完成設定並準備就緒了！ （您不需要設定其音訊會議提供者）。

如果您已使用協力廠商音訊會議提供者啟用使用者，您必須將這些使用者的提供者變更為 Microsoft。 若要變更使用者的提供者，請參閱[將 Microsoft 指派為音訊會議提供者](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

## <a name="step-3-other-admin-tasks"></a>步驟3：其他系統管理工作

下列步驟是**選擇性**的，但許多管理員都要執行這些步驟：

1. [自訂會議邀請](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。 為使用者設定的撥入號碼會自動新增至傳送給出席者的會議邀請中。 不過，您可以新增自己的說明與法律連結、文字訊息及小型公司圖形。

2. [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。 這是將顯示在由使用者排程之會議中的電話號碼。

3. [針對音訊會議設定自動語音](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)應答的語言，當電話撥入音訊會議電話號碼時，音訊會議自動語音應答會用來向來電者。 此步驟僅適用于您使用 Microsoft 作為音訊會議提供者的情況。

4. [為音訊會議會議設定 PIN 長度](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)。


> [!NOTE]
> 使用中國由世紀運營之 Office 365 的客戶尚不提供此功能。 若要深入瞭解，請參閱[瞭解由世紀運營的 Office 365](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)。

## <a name="related-topics"></a>相關主題

[在組織中啟用團隊](office-365-set-up.md)

[音訊會議的電話號碼](phone-numbers-for-audio-conferencing-in-teams.md)

[設定線上會議和電話會議的選項](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
