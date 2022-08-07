---
title: 在 Microsoft Teams 系統管理中心管理商務用 Skype設定
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
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
description: 瞭解如何在 Microsoft Teams 系統管理中心管理商務用 Skype功能的設定。
ms.openlocfilehash: 26b2ba51d42a7be227b513d72add3e34f07d0fcd
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269758"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理商務用 Skype設定

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

身為系統管理員，Microsoft Teams 系統管理中心是您管理貴組織中商務用 Skype使用者商務用 Skype功能的地方。 您可以在使用者詳細資料頁面的 **[商務用 Skype**] 索引 **標籤上**，于商務用 Skype頁面管理貴 [組織的](#manage-skype-for-business-settings-for-your-organization)設定，以及 [個別使用者](#manage-skype-for-business-settings-for-individual-users)的設定。

只有當貴組織的共存模式未設定為 **Teams** 時，您才會看到 **商務用 Skype** 頁面。 同樣地，如果使用者的共存模式並非僅限 Teams，您只會看到使用者的 **[商務用 Skype**]**索引標籤**。 若要深入瞭解共存模式，請參閱[瞭解 Teams 和商務用 Skype共存和互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)與[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> 商務用 Skype設定先前位於 Microsoft Teams 系統管理中心的 **舊版入口** 網站。 隨著舊版入口網站的淘汰，我們將設定移轉到 Teams 系統管理中心的這些新位置，以便商務用 Skype管理。

您必須被指派全域系統管理員或商務用 Skype系統管理員的[Azure AD 系統管理員角色](/azure/active-directory/roles/permissions-reference)，才能在 Microsoft Teams 系統管理中心管理商務用 Skype功能。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>管理貴組織的商務用 Skype設定

在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 **全組織設定**  >  **商務用 Skype**。 您可以在這裡為組織中的所有商務用 Skype使用者設定和管理Skype 會議廣播、目前狀態隱私權及行動裝置通知。

### <a name="skype-meeting-broadcast"></a>Skype 會議廣播

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

使用下列設定來管理貴組織中的[Skype 會議廣播](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="系統管理中心中Skype 會議廣播設定的螢幕擷取畫面。":::

- **Skype 會議廣播**：開啟此功能可為貴組織啟用Skype 會議廣播。 啟用此功能之後，您需要[設定Skype 會議廣播的網路](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **請參閱預覽功能**：開啟此功能以搶先使用新功能。
- **召集人可以排程匿名會議**：如果您想讓召集人建立廣播活動，允許組織外部的任何人加入，而不需要登入，請開啟此功能。 
- **錄製Skype 會議廣播會議**：開啟此功能可讓召集人和簡報者錄製會議。  
- **出席者的支援服務 URL**：輸入貴組織的支援 URL，會議出席者可在會議期間需要協助時使用 URL。

### <a name="presence-and-mobile-notifications"></a>目前狀態和行動裝置通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


使用下列設定來管理組織中的商務用 Skype目前狀態隱私權和行動裝置通知。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="系統管理中心中目前狀態設定的螢幕擷取畫面。":::

#### <a name="presence"></a>目前狀態

根據預設，貴組織商務用 Skype使用者可以查看其他商務用 Skype使用者的目前狀態 (，例如 [線上]、[忙碌] 或 [離開]) 。 選擇下列其中一項，以設定誰可以查看您的商務用 Skype使用者的目前狀態。

- **自動顯示目前狀態資訊**：貴組織中尚未新增至使用者 **外部** 或 **封鎖** 清單的任何商務用 Skype使用者，都可以看到該使用者的目前狀態。
- **只向使用者的連絡人顯示目前狀態資訊**：未新增至 **外部或****封鎖** 清單之使用者連絡人清單中的任何商務用 Skype使用者，都可以看到該使用者的目前狀態。 使用者可以在 商務用 Skype 中覆寫此設定，方法是移至 [**設定**  >  **工具選項**  >  **]**。

#### <a name="mobile-notifications"></a>行動裝置通知

您可以設定您的商務用 Skype行動使用者是否透過推入通知服務收到內送和未接立即訊息、語音信箱訊息和未接來電的相關通知。 視組織中使用的行動裝置而定，您可以使用 **Microsoft 推播通知服務**、 **Apple 推播通知服務** 或兩者。

請記住下列事項：

- 如果您關閉推播通知，使用者下次在行動裝置上啟動商務用 Skype時會收到所有通知。
- 根據預設，推入通知會開啟。 個別使用者可以在行動裝置上的商務用 Skype關閉。
- 當您關閉推播通知時，使用者無法將它們重新開啟。 

> [!IMPORTANT]
> Microsoft 會使用其他公司為Windows Phone、iPhone 和 iPad 使用者提供即時商務用 Skype行動通知。 請參閱本 [隱私權聲明](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>管理個別使用者的商務用 Skype設定

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

若要管理個別使用者的商務用 Skype設定，請在 Teams 系統管理中心的左側導覽中，移至 [**使用者**]，按一下使用者的顯示名稱以開啟使用者詳細資料頁面，然後選 **取 [商務用 Skype設定] 索引卷** 標。您可以在這裡為使用者設定外部存取和會議設定。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="使用者詳細資料頁面上商務用 Skype索引標籤的螢幕擷取畫面。":::

### <a name="external-access-settings"></a>外部存取設定

您可以選擇性地允許或封鎖使用者是否可以與組織外部人員通訊。

- **外部商務用 Skype使用者**：如果您要允許使用者與同盟網域中的商務用 Skype使用者通訊，請開啟此功能。
- **外部 Skype 使用者**：如果您想要允許使用者與 Skype 使用者通訊，請開啟此功能。 

### <a name="meeting-settings"></a>會議設定

您可以為使用者設定下列會議設定。

- **音訊&影片**：選擇下列其中一個音訊和視訊設定：

    - **無**：使用者無法使用音訊或視訊。
    - **僅限音訊**：使用者可以使用音訊，但不能使用視訊。
    - **音訊和視訊**：使用者可以使用音訊和視訊。
    - **音訊和視訊 (HD)**：使用者可以使用音訊和高畫質視訊。
    
- **錄製會議&交談**：開啟此功能以允許使用者錄製交談和會議。
- **合規性**：如果法律要求您保留電子儲存的資訊，請開啟此設定。