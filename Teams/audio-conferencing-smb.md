---
title: 設定音訊會議 - 中小型企業快速入門
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
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
description: 瞭解如何在中小型企業中為需要使用電話撥入會議的人員設定音訊會議。
ms.openlocfilehash: b3b3514e2d33abe53da940759ddacefea29b961a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270658"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>設定音訊會議 - 中小型企業快速入門

透過音訊會議，人員可以使用電話撥入 Teams 會議，而不用在行動裝置或電腦上使用 Teams 應用程式。  

如果您是擁有最多 300 個使用者的中小型企業，而且目前沒有任何音訊會議授權，您可以免費取得一年的音訊會議。 此免費優惠從 2020 年 10 月 1 日開始提供。

音訊會議附加元件授權可以套用至擁有Microsoft 365 商務基本版、商務標準版、商務進階版、企業版 E1 或企業版 E3 授權的使用者。 若要深入瞭解，請參閱 [Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> 如果您有企業版 E5 或 Microsoft 365 商務語音，您將無法使用免費的音訊會議優惠，因為這些授權已包含音訊會議。

在本文中，我們將逐步引導您設定音訊會議。 您只需要為打算排程或主持會議的人員設定音訊會議即可。 撥入會議的會議出席者不需要授權或其他設定。 若要深入瞭解，請參閱 [音訊會議](audio-conferencing-in-office-365.md)。

## <a name="set-up-audio-conferencing"></a>設定音訊會議

當您設定音訊會議時，會自動將電話號碼指派到您的會議橋接器，以便在會議邀請中使用。 指派為會議橋接器預設號碼的電話號碼，會是貴組織國家或地區所提供的電話號碼。 這個電話號碼是付費電話號碼，可能需要支付長途電話費用。

> [!NOTE]
> 您也可以使用免付費電話號碼，這需要幾個額外的步驟。 若要深入瞭解會議橋接器的電話號碼，請參閱本文稍後的 [音訊會議電話號碼](#audio-conferencing-phone-numbers) 。

### <a name="step-1-get-audio-conferencing-licenses"></a>步驟 1：取得音訊會議授權

為每位主持會議的人員取得一個音訊會議授權。 使用Microsoft 365 系統管理中心執行此動作。

1. 在Microsoft 365 系統管理中心中，移至 **[計費**  >  **購買服務**]，然後在頁面底部選取 **[附加元件]**。
2. 選 **取 [Microsoft 365 音訊會議採用促銷**  >  **詳細資料]**，然後選取 [**立即取得]**。
3. 輸入會議召集人所需的授權數目，然後完成訂單。

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="音訊會議採用促銷授權的螢幕擷取畫面。":::

    > [!NOTE]
    > 清除或選取 **[自動指派給所有沒有授權的使用者**]，視您是否要自動指派音訊會議授權給沒有此授權的所有使用者而定。

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>步驟 2：指派音訊會議授權給主持會議的使用者

指派授權給主持會議的每個人員。 使用Microsoft 365 系統管理中心執行此動作。

#### <a name="assign-a-license-to-one-user"></a>指派授權給一位使用者

1. 在Microsoft 365 系統管理中心中，移至 **[使用者**  >  **作用中使用者]**。  
2. 選取您要指派授權的使用者列，然後在窗格中選取 **[授權與應用程式]**。
3. 選取 [ **Microsoft 365 音訊會議] 複** 選框，然後選取 [ **儲存變更]**。

#### <a name="assign-a-license-to-multiple-users"></a>指派授權給多位使用者

1. 在Microsoft 365 系統管理中心中，移至 **[使用者**  >  **作用中使用者]**。  
2. 選取您要指派授權的使用者旁邊的圓圈，然後選取 **[管理產品授權]**。
3. 在 [ **管理產品授權** ] 窗格中，選 **取 [指派更多]**。
4. 選取 [ **Microsoft 365 音訊會議] 複** 選框，然後選取 [ **儲存變更]**。  

> [!IMPORTANT]
> 指派的電話號碼最多可能需要 24 小時，才會顯示在您的會議邀請上。 如果您沒有看到更新號碼出現，請等候至少 24 小時，然後再連絡支援服務。

## <a name="schedule-teams-meetings-in-outlook"></a>在 Outlook 中排程 Teams 會議

您的會議召集人現在可以在 Outlook 中排程會議。 在 Outlook 中，移至 [ **行事曆**]，然後選取 [ **新增 Teams 會議** ] 按鈕。 會議撥入號碼和會議 ID 會自動新增至傳送給會議出席者的會議邀請。 若要深入瞭解，請參閱 [在 Outlook 中排程 Teams 會議](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)。

> [!NOTE]
> 如有需要，您可以自訂會議邀請來新增公司標誌、支援網站連結和法律免責聲明，以及僅限文字的頁尾。 若要深入瞭解，請參閱 [自訂會議邀請](meeting-settings-in-teams.md#customize-meeting-invitations)。

## <a name="audio-conferencing-phone-numbers"></a>音訊會議電話號碼

有兩種類型的數位可供您用於會議橋接器。 You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**. 以下是每個應用程式的詳細資訊。

### <a name="shared-numbers"></a>共用號碼

共用號碼是一個在所有組織之間共用的數位。 共用號碼是付費電話號碼，且會在您設定音訊會議時自動指派。

若要查看指派給會議橋接器的預設號碼，請在 Microsoft Teams 系統管理中心的左側導覽中，移至 **會議**  >  **橋**，然後尋找最接近您的位置號碼。

### <a name="dedicated-numbers"></a>專用號碼

專用號碼是一個僅供使用者使用的號碼。 專用號碼可以是付費電話號碼或免付費電話號碼。 若要使用專用號碼，您必須先取得號碼、指派給會議橋接器，然後將號碼指派給主持會議的每個人員。

有幾種方法可以取得專用號碼。 您可以從 Microsoft 取得號碼，或將 (埠) 您目前服務提供者的現有號碼移轉到 Microsoft。 若要深入瞭解做法，請參閱 [取得服務號碼](getting-service-phone-numbers.md)。

請記住，如果您使用免付費電話號碼，您必須先指派通訊點數授權給主持會議的每個人員。 若要深入瞭解，請參閱 [為您的組織設定通訊點](set-up-communications-credits-for-your-organization.md)數。

取得您的號碼之後，請將它指派到會議橋接器。 使用 Microsoft Teams 系統管理中心執行此動作。

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 **會議**  >  **橋接器**。
2. 選取 **[新增**]，然後選取 **[付費電話號碼** ] 或 **[免付費電話號碼]**。
3. 在 [ **新增電話號碼** ] 窗格中，選取號碼，然後選取 [ **套用]**。

#### <a name="assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>為主持會議的使用者指派撥入電話號碼

請參閱 [在 Microsoft Teams 中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。

> [!NOTE]
> 您也可以將電話號碼新增至 *TeamsAudioconferencingpolicy* ，並將原則指派給使用者，藉此設定電話號碼。 新增到原則的付費和免付費電話號碼會優先于透過音訊會議設定窗格個別為使用者設定的電話號碼。 如果未將電話號碼新增至 *Teamsaudioconferencingpolicy*，則透過音訊會議設定窗格個別為使用者設定的電話號碼將會顯示在 Microsoft Teams 會議邀請中。 [付費和免付費電話號碼的音訊會議原則設定](audio-conferencing-toll-free-numbers-policy.md) 有更多資訊。

## <a name="related-topics"></a>相關主題

- [音訊會議](audio-conferencing-in-office-365.md)
- [設定 Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)
- [音訊會議的電話號碼](phone-numbers-for-audio-conferencing-in-teams.md)
- [音訊會議的常見問題](audio-conferencing-common-questions.md)
- [取得服務號碼](getting-service-phone-numbers.md)
- [Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)
