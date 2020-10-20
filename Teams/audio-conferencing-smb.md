---
title: 針對中小型企業設定音訊會議
ms.author: v-lanac
author: lanachin
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '瞭解如何在中小型企業中為需要使用電話撥入會議的人員設定音訊會議。 '
ms.openlocfilehash: b692654a0a874ea0c07f074daefe203aef2f80bc
ms.sourcegitcommit: 764605e226bc7d9cf45e9833c758d30da29132c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594644"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>針對中小型企業設定音訊會議

透過音訊會議，使用者可以使用電話撥入團隊會議，而不是在行動裝置或電腦上使用 [小組] 應用程式。  

如果您是最多300個使用者的中小型企業或中型企業，而且您目前沒有任何音訊會議授權，您可以在一年免費取得語音會議。 此免費優惠于2020年10月1日起提供。

您可以將音訊會議附加元件授權套用至擁有 Microsoft 365 商務基本版、商務標準版、Business Premium、企業版 E1 或企業版 E3 授權的使用者。 若要深入瞭解，請參閱 [小組附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> 如果您有企業版 E5 或 Microsoft 365 商務語音，您將無法使用免費的音訊會議優惠，因為這些授權已包含音訊會議。

在本文中，我們將逐步引導您瞭解如何設定音訊會議。 您只需要為打算排程或主持會議的人員設定音訊會議即可。 呼叫會議的出席者不需要授權或其他設定。 若要深入瞭解，請參閱 [音訊會議](audio-conferencing-in-office-365.md)。

## <a name="set-up-audio-conferencing"></a>設定音訊會議

當您設定音訊會議時，系統會自動將電話號碼指派給您的會議橋接器，以便在會議邀請中使用。 指派為會議橋接器預設號碼的電話號碼將是貴組織的國家或地區。 此電話號碼是收費的電話號碼，可能需要支付長途費用。

> [!NOTE]
> 您也可以使用免付費電話號碼，這需要幾個額外的步驟。 若要深入瞭解您的會議橋接器的電話號碼，請參閱本文稍後的 [音訊會議電話號碼](#audio-conferencing-phone-numbers) 。

### <a name="step-1-get-audio-conferencing-licenses"></a>步驟1：取得音訊會議授權

針對將領導會議的每位人員，取得一個音訊會議授權。 使用 Microsoft 365 系統管理中心來執行此動作。

1. 在 Microsoft 365 系統管理中心中，移至 [**帳單**  >  **購買服務**]，然後按一下頁面底部的 [**附加**元件]。
2. 選取 [ **Microsoft 365 音訊會議採納促銷**  >  **詳細資料**]，然後選取 [**立即取得**]。
3. 輸入會議召集人所需的授權數量，然後完成您的訂單。

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="音訊會議採用促銷授權的螢幕擷取畫面":::

    > [!NOTE]
    > 根據您是否要將音訊會議授權自動指派給沒有此授權的所有使用者，清除或選取 [ **自動指派給沒有授權的所有使用者**]。

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>步驟2：指派音訊會議授權給領導會議的使用者

指派授權給將領導會議的每一個人。 使用 Microsoft 365 系統管理中心來執行此動作。

#### <a name="assign-a-license-to-one-user"></a>指派授權給一個使用者

1. 在 Microsoft 365 系統管理中心中，移至 [**使用者**作用中的  >  **使用者**]。  
2. 選取您要指派授權的使用者列，然後在窗格中選取 [ **授權及應用程式**]。
3. 選取 [ **Microsoft 365 音訊會議** ] 核取方塊，然後選取 [ **儲存變更**]。

#### <a name="assign-a-license-to-multiple-users"></a>指派授權給多位使用者

1. 在 Microsoft 365 系統管理中心中，移至 [**使用者**作用中的  >  **使用者**]。  
2. 選取您要指派授權的使用者旁邊的圓圈，然後選取 [ **管理產品授權**]。
3. 在 [ **管理產品授權** ] 窗格中，選取 [ **指派更多**]。
4. 選取 [ **Microsoft 365 音訊會議** ] 核取方塊，然後選取 [ **儲存變更**]。  

## <a name="schedule-teams-meetings-in-outlook"></a>在 Outlook 中排程團隊會議

您的會議召集人現在可以在 Outlook 中排程會議。 在 Outlook 中，移至 [行事 **曆**]，然後選取 [ **新增團隊會議** ] 按鈕。 會議撥入號碼和會議 ID 會自動新增至傳送給會議出席者的會議邀請中。 若要深入瞭解，請參閱 [在 Outlook 中排程團隊會議](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)。

> [!NOTE]
> 如有需要，您可以自訂會議邀請來新增公司標誌、支援網站的連結和法律免責聲明，以及純文字的頁尾。 若要深入瞭解，請參閱 [自訂會議邀請](meeting-settings-in-teams.md#customize-meeting-invitations)。

## <a name="audio-conferencing-phone-numbers"></a>音訊會議電話號碼

您可以在會議橋接器中使用兩種類型的數位。 您可以在本文前面的[設定音訊會議](#set-up-audio-conferencing)區段中使用**共用號碼** (，) 或**專屬號碼**。 以下是每個程式的詳細資訊。

### <a name="shared-numbers"></a>共用號碼

共用號碼是在所有組織間共用的數位。 共用號碼是付費電話號碼，當您設定音訊會議時，系統會自動指派它。

若要查看指派給您會議橋接器的預設號碼，請在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議橋接**]，然後找出最接近您的位置號碼。

### <a name="dedicated-numbers"></a>專用號碼

[專用號碼] 是只有您的使用者可以使用的數位。 專用號碼可以是收費電話號碼或免付費電話號碼。 若要使用專用號碼，您必須先取得該號碼、將它指派給您的會議橋接器，然後將該號碼指派給將領導會議的每一個人。

有幾種方法可以取得專用號碼。 您可以從 Microsoft 取得號碼，或將現有的號碼從目前的服務提供者)  (埠轉接至 Microsoft。 若要深入瞭解如何執行此動作，請參閱 [取得服務電話號碼](getting-service-phone-numbers.md)。

請記住，如果您使用免付費電話號碼，您必須先將通訊信用授權指派給將領導會議的每一個人。 若要深入瞭解，請參閱 [為您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。

您有號碼之後，請將它指派給您的會議橋接器。 使用 Microsoft 團隊系統管理中心來執行此動作。

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議橋**]。
2. 選取 [ **新增**]，然後選取 [ **付費電話號碼** ] 或 [ **免付費電話號碼**]。
3. 在 [ **新增電話號碼** ] 窗格中 **，選取該**號碼，然後選取 [套用]。

然後，將該號碼指派給將領導會議的每一個人。 使用 Microsoft 團隊系統管理中心來執行此動作。

1. 在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **使用者**]，按一下使用者的顯示名稱，然後選取 [ **編輯**]。
2. 選取 **Edit**[    **音訊會議**] 旁的 [編輯]，然後在 [ **音訊會議**   ] 窗格中，選取 [ **付費電話號碼**]   或 [ **免付費電話**號碼] 清單中的數位   ，然後選取**Apply**[套用]。

## <a name="related-topics"></a>相關主題

- [音訊會議](audio-conferencing-in-office-365.md)
- [為小組設定音訊會議](set-up-audio-conferencing-in-teams.md)
- [音訊會議的電話號碼](phone-numbers-for-audio-conferencing-in-teams.md)
- [音訊會議的常見問題](audio-conferencing-common-questions.md)
- [取得服務號碼](getting-service-phone-numbers.md)
- [團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
