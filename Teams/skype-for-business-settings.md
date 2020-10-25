---
title: 管理 Microsoft 團隊系統管理中心中的商務用 Skype 設定
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊系統管理中心管理商務用 Skype 功能的設定。
ms.openlocfilehash: 18f1de99964a36485e69a210c71b6350313aa1cb
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753558"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>管理 Microsoft 團隊系統管理中心中的商務用 Skype 設定

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

做為管理員，Microsoft [團隊管理中心] 是您在其中管理組織中商務用 Skype 使用者的商務用 Skype 功能。 您可以在 [**商務用 skype** ] 頁面上管理[貴組織](#manage-skype-for-business-settings-for-your-organization)的設定，以及在 [使用者詳細資料] 頁面的 [**商務用 skype** ] 索引標籤上的[個別使用者](#manage-skype-for-business-settings-for-individual-users)設定。

如果貴組織的共存模式未設定為 [**僅限團隊**]，您就只會看到 [**商務用 Skype** ] 頁面。 同樣地，如果使用者的共存模式不是**團隊**，您就只會看到使用者的 [**商務用 Skype** ] 索引標籤。 若要深入瞭解共存模式，請參閱 [瞭解團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ，以及 [設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> 商務用 Skype 設定先前位於 Microsoft 團隊系統管理中心的 **舊版入口網站** 中。 在停用舊版入口網站之後，我們會將設定遷移至 [團隊管理中心] 中的 [商務用 Skype 管理] 的新位置。

您必須獲指派全域系統管理員或商務用 Skype 系統管理員的 [AZURE AD 管理員角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能在 Microsoft 團隊系統管理中心管理商務用 skype 功能。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>管理貴組織的商務用 Skype 設定

在 Microsoft [團隊管理中心] 的左導覽中，移至 [**全組織性設定**  >  **商務用 Skype**]。 您可以從這裡設定及管理貴組織中所有商務用 Skype 使用者的 Skype 會議廣播、目前狀態隱私權及行動裝置通知。

### <a name="skype-meeting-broadcast"></a>Skype 會議廣播

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

使用下列設定管理組織中的 [Skype 會議廣播](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="系統管理中心 Skype 會議廣播設定的螢幕擷取畫面":::

- **Skype 會議廣播**：開啟此功能可為您的組織啟用 Skype 會議廣播。 啟用此功能之後，您必須為 [Skype 會議廣播設定您的網路](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **請參閱預覽功能**：開啟此功能可提前取得新功能的存取權。
- **召集人可以排程匿名會議**：如果您想要讓召集人建立廣播事件，讓組織外的任何人都能加入，而不需要登入，請開啟此選項。 
- **錄製 Skype 會議廣播會議**：開啟此功能可讓召集人和簡報者錄製會議。  
- 協助者**支援網址**：如果會議期間需要協助，請輸入您組織的支援 url，會議出席者就可以使用。

### <a name="presence-and-mobile-notifications"></a>目前狀態與行動裝置通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


使用下列設定來管理貴組織中的商務用 Skype 目前狀態隱私權與行動通知。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="系統管理中心 [目前狀態] 設定的螢幕擷取畫面":::

#### <a name="presence"></a>目前狀態

根據預設，貴組織中的商務用 Skype 使用者可以在其他商務用 Skype 使用者的 [可用]、[忙碌] 或 [離開]) 看到目前狀態 (。 選擇下列其中一項，設定誰可以查看您的商務用 Skype 使用者的目前狀態。

- **自動顯示目前狀態資訊**：貴組織中尚未新增至使用者的 **外部** 或 **封鎖** 清單的任何商務用 Skype 使用者，都可以看到該使用者的目前狀態。
- **只向使用者的連絡人顯示目前狀態資訊**：使用者連絡人清單中未新增至其 **外部** 或 **封鎖** 清單的任何商務用 Skype 使用者，都可以看到該使用者的目前狀態。 使用者可以移至 [**設定**  >  **工具**]  >  **選項**，在商務用 Skype 中覆寫此設定。

#### <a name="mobile-notifications"></a>行動裝置通知

您可以設定您的商務用 Skype 行動使用者是否會透過推播通知服務接收和未接的立即訊息、語音信箱訊息和未接來電發出通知。 視貴組織中使用的行動裝置而定，您可以使用 **Microsoft 推播通知服務**、 **Apple 推播通知服務**，或同時使用兩者。

請記住下列事項：

- 如果您關閉推播通知，當使用者下次在行動裝置上啟動商務用 Skype 時，就會收到所有通知。
- 預設會開啟推播通知。 個別使用者可以在行動裝置的商務用 Skype 中關閉它們。
- 當您關閉推播通知時，使用者將無法再次開啟推播通知。 

> [!IMPORTANT]
> Microsoft 使用其他公司為 Windows Phone、iPhone 和 iPad 使用者提供即時商務用 Skype mobile 通知。 請參閱本 [隱私權聲明](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>管理個別使用者的商務用 Skype 設定

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

若要管理個別使用者的商務用 Skype 設定，請移至 [團隊管理中心] 的左導覽，移至 [ **使用者**]，按一下使用者的顯示名稱以開啟 [使用者詳細資料] 頁面，然後選取 [ **商務用 Skype 設定** ] 索引標籤。您可以從這裡設定使用者的外部存取與會議設定。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="[使用者詳細資料] 頁面的 [商務用 Skype] 索引標籤螢幕擷取畫面":::

### <a name="external-access-settings"></a>外部存取設定

您可以選擇性地允許或封鎖使用者是否能與組織外部的人員進行通訊。

- **外部商務用 Skype 使用者**：如果您想要允許使用者與聯盟網域中的商務用 skype 使用者通訊，請開啟此選項。
- **外部 Skype 使用者**：如果您想要允許使用者與 Skype 使用者通訊，請開啟此選項。 

### <a name="meeting-settings"></a>會議設定

您可以為使用者設定下列會議設定。

- **音訊 & 影片**：選擇下列其中一個音訊和影片設定：

    - **None**：使用者無法使用音訊或視頻。
    - **僅音訊**：使用者可以使用音訊，但不能使用影片。
    - **音訊與影片**：使用者可以使用音訊和影片。
    - **音訊與影片 (高清) **：使用者可以使用音訊和高清影片。
    
- **錄製交談 & 會議**：開啟此功能可讓使用者記錄交談和會議。
- **合規性**：如果您在法律上需要保留以電子方式儲存的資訊，請開啟此選項。 
