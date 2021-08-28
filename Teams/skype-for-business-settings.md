---
title: 在 商務用 Skype 系統管理中心管理Microsoft Teams設定
author: cichur
ms.author: v-cichur
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在系統管理中心管理商務用 Skype功能Microsoft Teams設定。
ms.openlocfilehash: e3679f80057349b60af9bc11b2aa43c3ceb6a431
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636437"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>在 商務用 Skype 系統管理中心管理Microsoft Teams設定

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

作為系統管理員，Microsoft Teams管理中心是管理組織中商務用 Skype使用者商務用 Skype功能的地方。 您可以管理組織[在](#manage-skype-for-business-settings-for-your-organization)商務用 Skype 頁面上的設定，以及使用者詳細資料頁面[](#manage-skype-for-business-settings-for-individual-users)的 商務用 Skype 索引商務用 Skype個別使用者的設定。 

如果貴組織的共存商務用 Skype未設為只顯示 ，您只會看到 Teams **頁面**。 同樣地，您只會看到使用者的商務用 Skype，如果使用者的共存模式不是只Teams **的。** 若要深入瞭解共存模式，請參閱瞭解Teams及商務用 Skype及互通性，[以及](teams-and-skypeforbusiness-coexistence-and-interoperability.md)設定[您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> 商務用 Skype系統管理中心的舊版入口網站中Microsoft Teams設定。 舊版入口網站已停用後，我們已將設定移Teams系統管理商務用 Skype位置。

您必須指派全域系統管理員或系統管理員的[Azure AD](/azure/active-directory/roles/permissions-reference)系統管理員商務用 Skype，才能商務用 Skype系統管理中心Microsoft Teams功能。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>管理商務用 Skype的設定

在系統管理中心的左側導Microsoft Teams，請前往整個 **組織設定**  >  商務用 Skype。 您可以在這裡為貴組織Skype使用者設定及管理會議廣播、目前狀態隱私權商務用 Skype行動裝置通知。

### <a name="skype-meeting-broadcast"></a>Skype 會議廣播

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

使用下列設定來管理[Skype會議](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)廣播。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="系統管理Skype會議廣播設定螢幕擷取畫面":::

- **Skype會議廣播**：開啟此選項，Skype組織的會議廣播。 啟用這項功能後，您必須設定您的網路以Skype[廣播](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **請參閱預覽功能**：開啟此功能以提早存取新功能。
- **召集人可以排程匿名會議**：如果您想要讓召集人建立廣播活動，讓組織外部的任何人無需登錄即可加入，請開啟此功能。 
- **錄製Skype廣播會議**：開啟此功能，讓召集人和簡報者錄製會議。  
- **出席者的支援 URL：** 輸入貴組織的支援 URL，如果出席者在會議期間需要協助，可以使用該 URL。

### <a name="presence-and-mobile-notifications"></a>目前狀態與行動通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


使用下列設定來管理商務用 Skype目前狀態隱私權和行動通知。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="系統管理中心目前狀態設定螢幕擷取畫面":::

#### <a name="presence"></a>目前狀態

根據預設，商務用 Skype中的使用者可以看到其他使用者目前狀態 (例如可用、忙碌) 離開商務用 Skype狀態。 選擇下列其中一項來設定誰可以看到您的商務用 Skype使用者。

- **自動顯示目前狀態** 資訊：商務用 Skype組織中尚未新增到使用者的外部或封鎖清單的任何使用者，都可以看到該使用者的目前狀態。 
- 只 **向** 使用者的連絡人顯示目前狀態資訊：商務用 Skype連絡人清單中未新增到其外部或封鎖清單中的任何 商務用 Skype 使用者，都能看到該使用者的目前狀態。   使用者可以在 商務用 Skype 中設定此設定 **，設定**  >  **工具**  >  **選項**。

#### <a name="mobile-notifications"></a>行動通知

您可以設定您的行動商務用 Skype使用者是否透過推入通知服務收到有關傳入和未接立即訊息、語音信箱訊息和未接來電的提醒。 視貴組織中所使用的行動裝置不同，您可以使用 Microsoft 推入通知 **服務****、Apple 推入通知服務**，或兩者同時使用。

請記住下列事項：

- 如果您關閉推入通知，使用者下次在行動裝置上商務用 Skype收到所有通知。
- 根據預設，推入通知會開啟。 個別使用者可以在行動裝置上商務用 Skype關閉這些裝置。
- 當您關閉推入通知時，使用者無法重新開啟。 

> [!IMPORTANT]
> Microsoft 會使用其他公司為商務用 Skype使用者提供即時Windows Phone iPhone通知iPad通知。 請參閱本 [隱私權聲明](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>管理商務用 Skype使用者的設定

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

若要管理商務用 Skype的使用者設定，請在 Teams 系統管理中心的左側流覽中，前往 [使用者」，按一下使用者的顯示名稱以開啟使用者詳細資料頁面，然後選取 [商務用 Skype **設定>** 定位點。您可以在這裡為使用者設定外部存取和會議設定。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="使用者詳細商務用 Skype頁面上的 商務用 Skype的螢幕擷取畫面":::

### <a name="external-access-settings"></a>外部存取設定

您可以選擇性地允許或封鎖使用者是否能與組織外部人員通訊。

- **外部商務用 Skype** 使用者：如果您想要允許使用者與在商務用 Skype網域中的使用者通訊，請開啟此功能。
- **外部Skype** 使用者：如果您想要允許使用者與使用者通訊，請開啟Skype。 

### <a name="meeting-settings"></a>會議設定

您可以為使用者設定下列會議設定。

- **音訊&視** 訊：選擇下列其中一個音訊和視訊設定：

    - **無**：使用者無法使用音訊或視訊。
    - **僅音訊**：使用者可以使用音訊，但不得使用視訊。
    - **音訊和視訊**：使用者可以使用音訊和視訊。
    - **音訊和視訊 (HD) ：** 使用者可以使用音訊和高畫質視訊。
    
- **錄製&** 交談：開啟此選項以允許使用者錄製交談和會議。
- **合規性**：如果您依法需要保留以電子方式儲存的資訊，請開啟此功能。