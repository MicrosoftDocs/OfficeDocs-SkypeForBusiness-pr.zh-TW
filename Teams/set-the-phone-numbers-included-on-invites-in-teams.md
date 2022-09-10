---
title: 設定邀請中包含的電話號碼
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
- seo-marvel-mar2020
description: 請依照下列步驟建立預設電話號碼，讓來電者加入 Microsoft Teams 會議。
ms.openlocfilehash: 27ff7040b27d2265bcdc5ab30f48cb919746471b
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642064"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>在 Microsoft Teams 中設定邀請中包含的電話號碼

Microsoft 365 和 Office 365 中的音訊會議可讓貴組織中的使用者建立 Microsoft Teams 會議，然後允許使用者使用電話號碼撥入這些會議。

會議橋接器可為您的組織提供一組撥入電話號碼。 所有會議都可以用來加入會議召集人建立的會議，但您可以選取會議邀請中會包含哪些會議。

除了會議召集人會議邀請中包含的電話號碼之外，每個會議邀請底部也會有一個連結，其中會開啟所有可用來加入會議之撥入電話號碼的完整清單。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-users"></a>為使用者初始指派會議邀請中包含的電話號碼

在已指派給使用者的 *TeamsAudioConferencingPolicy* 中定義了會議邀請中已啟用音訊會議之使用者的電話號碼。 當 *TeamsAudioConferencingPolicy* 指派給使用者時，原則中新增的所有付費和免付費電話號碼都會包含在具有該原則的使用者的會議邀請中。 如果使用者獲指派 *TeamsAudioConferencingPolicy* ，且原則中未新增任何付費或免付費電話號碼，則在這種情況下，這些使用者會議邀請中顯示的電話號碼會根據預設會議付費電話號碼和每個個別使用者設定中的預設會議免付費電話號碼來定義。

> [!NOTE]
> 新增到 *TeamsAudioConferencingPolicy* 的付費或免付費電話號碼會優先于使用者設定的預設會議付費電話號碼和預設會議免付費電話號碼個別設定的電話號碼。

如上所述，除了電話號碼之外，每一個會議邀請都包含一個連結，該連結會開啟所有可用來加入指定會議之撥入電話號碼的完整清單。

> [!IMPORTANT]
> 指派的電話號碼最多可能需要 24 小時，才會顯示在您的會議邀請上。 如果您沒有看到更新號碼出現，請等候至少 24 小時，然後再連絡支援服務。

### <a name="new-users"></a>新使用者

會議邀請中包含給新使用者的付費電話號碼和免付費電話號碼，也會由指派給這些使用者的 *TeamsAudioconferencingPolicy* 定義。 根據預設，所有新使用者都會獲派 Global *TeamsAudioconferencingPolicy*。 除非租使用者系統管理員) 變更此設定，否則全域原則不會新增任何電話號碼 (。 在此情況下，已啟用音訊會議之使用者之會議邀請中所包含的電話號碼，會根據每個使用者設定中找到的預設會議付費電話號碼和預設會議免付費電話號碼來定義。

對於新使用者，預設的會議付費號碼會根據使用者在啟用音訊會議服務時，使用者 Microsoft 365 系統管理中心的 [使用位置] 設定來指派預設會議付費電話號碼。 如果會議橋接器中有符合使用者國家/地區的付費電話號碼，該號碼會自動指派為使用者的預設付費電話號碼。 如果沒有，系統會將定義為會議橋接器預設付費電話號碼的數位指派為使用者的預設付費電話號碼。  

一旦使用者啟用音訊會議服務，租使用者系統管理員就可以視需要變更使用者的預設付費電話號碼和免付費電話號碼。

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-users-in-powershell-using-the-teamsaudioconferencingpolicy-cmdlet"></a>在 Powershell 中使用 *TeamsAudioConferencingPolicy* Cmdlet 設定或變更使用者的預設音訊會議電話號碼

請參閱 [付費和免付費電話號碼的音訊會議原則設定](audio-conferencing-toll-free-numbers-policy.md)

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user-individually"></a>設定或變更會議召集人或使用者的預設音訊會議電話號碼

您必須是 Teams 服務系統管理員才能進行這些變更。 請參閱[使用 Teams 系統管理員角色來管理 Teams](./using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 登入 Microsoft Teams 系統管理中心。

2. 在左側導覽中，按一下 [ **使用者]**。

    ![顯示在 Microsoft Teams 系統管理中心選取使用者。](media/Admin-users.png)

3. 從可用使用者清單中按一下使用者名稱。

4. 在 **[音訊會議**] 旁邊，按一下 [ **編輯]**。

    ![按一下 [音訊會議] 旁的 [編輯]。](media/teams-set-phone-numbers-on-invites-image3.png)

5. 使用 **[付費號碼** ] 或 **[免付費號碼** ] 欄位輸入使用者的號碼。

> [!IMPORTANT]
> 當您變更使用者的音訊會議設定時，必須更新週期性及未來的 Microsoft Teams 會議並傳送給出席者。

> [!NOTE]
> 只有在指派給使用者的 *TeamsAudioConferencingPolicy* 沒有新增任何電話號碼時，才會使用此設定中輸入的電話號碼。

## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化當您有多個工作要執行的日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))

若要設定或變更會議召集人或使用者使用 [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)的預設音訊會議電話號碼，請將 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) Cmdlet 的其中一個可用號碼設定 **`ServiceNumber`** 或 **`TollFreeServiceNumber`** 參數。

## <a name="related-topics"></a>相關主題

[在 Microsoft Teams 版 Microsoft 365 中試用或購買音訊會議](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)

[變更音訊會議橋接器的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
