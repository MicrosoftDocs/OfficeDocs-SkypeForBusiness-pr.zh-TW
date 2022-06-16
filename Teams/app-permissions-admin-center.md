---
title: 在 Microsoft Teams 系統管理中心檢視應用程式許可權並授與系統管理員同意
author: guptaashish
ms.author: guptaashish
ms.reviewer: vaibhava
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在系統管理中心的 [管理應用程式] 頁面上檢視應用程式要求的許可權，以及將系統管理員同意授 Microsoft Teams與應用程式。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e81b15b700cf2b62c93e5acd784a6303458280aa
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124438"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心檢視應用程式許可權並授與系統管理員同意

您可在系統管理中心Microsoft Teams [[管理應用程式](manage-apps.md)] 頁面，檢視和管理貴組織的所有Teams應用程式。 例如，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式至貴組織的 App 市集、在組織層級封鎖或允許應用程式，以及管理整個組織的應用程式設定。

您也可以在這裡將整個組織的系統管理員同意授與應用程式，以要求存取資料的許可權，並檢視資源特定同意 (RSC) 應用程式的許可權。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>將整個組織的系統管理員同意授與應用程式

如果您是全域系統管理員，您可以檢閱並授與同意可代表貴組織中所有使用者要求許可權的應用程式。 如此一來，使用者就不必在啟動應用程式時，檢閱並接受應用程式要求的許可權。 此外，根據 Azure Active Directory (Azure AD) 中的使用者[同意設定](/azure/active-directory/manage-apps/configure-user-consent)，某些使用者可能無法將同意授與存取公司資料的應用程式。

應用程式要求的許可權範例包括讀取儲存在小組中的資訊、讀取使用者的設定檔，以及代表使用者傳送電子郵件的功能。 若要深入瞭解，請參閱[Microsoft 身分識別平臺端點中的許可權與同意](/azure/active-directory/develop/v2-permissions-and-consent)。

[ **許可權]** 欄會指出應用程式是否有需要同意的許可權。 您會看到在 Azure AD 中註冊的每個應用程式的 [檢 **視詳細資料** ] 連結，該應用程式具有需要同意的許可權。 請記住，這僅適用于自訂和協力廠商應用程式。 此連結不適用於 Microsoft 提供的應用程式。 此外，系統管理員不需要針對這類應用程式授與同意。

若要授與整個組織對應用程式的同意，請依照下列步驟進行：

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **Teams應用程式**  >  **[管理應用程式。](https://admin.teams.microsoft.com/policies/manage-apps)**

1. 執行下列其中一項：
    * 搜尋您想要的應用程式，按一下應用程式名稱以移至應用程式詳細資料頁面，然後選取 [ **許可權] 索引卷** 標。
    * 以遞減順序排序 [ **許可權** ] 欄以尋找應用程式，然後選 **取 [檢視詳細資料]**。 這麼做會將您帶到應用程式詳細資料頁面的 [許可權] 索引 **標籤。**

1. 在 **[全組織許可權] 底** 下，選取 [ **檢閱許可權與同意]**。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="應用程式 [許可權] 索引標籤上全組織許可權的螢幕擷取畫面。":::

    您必須是全域系統管理員才能執行此動作。 Teams服務系統管理員無法使用此選項。

1. 在 [ **許可權] 索引卷** 標上，檢閱應用程式要求的許可權。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="應用程式要求許可權的螢幕擷取畫面。":::

    > [!IMPORTANT]
    > 授與整個組織同意的應用程式可讓應用程式存取您組織的資料。 在您授與同意之前，請仔細檢閱應用程式要求的許可權。

1. 如果您同意應用程式要求的許可權，請按一下 [ **接受** ] 以授與同意。 橫幅會暫時顯示在頁面頂端，讓您知道已授與應用程式的許可權。 應用程式現在可以存取貴組織中所有使用者的指定資源，而且不會提示其他人檢閱許可權。

接受許可權後，您會在應用程式詳細資料頁面的 [ **整個組織權** 限] 底下看到一則訊息，讓您知道已授與同意。 若要檢視應用程式許可權的詳細資料，請按一下 **Azure Active Directory** 連結，前往 Azure AD 入口網站中的應用程式頁面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="核准同意時顯示訊息的螢幕擷取畫面。":::

如果貴組織中的使用者可以授與同意，而且如果有一或多個使用者同意特定的應用程式，您也會看到相同的訊息，讓您知道已授與同意，以及Azure Active Directory Azure AD 入口網站中應用程式頁面的連結。

> [!NOTE]
> 雖然Teams服務管理員無法使用 [**檢閱許可權與同意**] 選項，而且他們無法將全組織的系統管理員同意授與應用程式，Teams服務系統管理員可以在應用程式的 [**權** 限] 索引標籤上檢視內容。 例如，Teams服務系統管理員可以按一下 **Azure Active Directory** 連結，在 Azure AD 入口網站中檢視應用程式許可權詳細資料。

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>檢視應用程式的資源特定同意許可權

RSC 許可權可讓團隊擁有者同意應用程式存取及修改團隊資料。 RSC 許可權是精細的Teams特定許可權，可定義應用程式可在特定團隊中執行的動作。 RSC 許可權的範例包括建立和刪除頻道、取得團隊的設定，以及建立和移除頻道索引標籤的功能。

RSC 許可權是在應用程式資訊清單中定義，而不是在 Azure AD 中。 當您將應用程式新增至團隊時，即表示同意 RSC 許可權。 若要深入瞭解，請參閱 [資源特定同意 (RSC) ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

全域系統管理員和Teams服務系統管理員可以在應用程式詳細資料頁面的 [**權** 限] 索引標籤上，檢視應用程式的 RSC 許可權。

若要檢視應用程式的 RSC 許可權，請遵循下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
1. 搜尋您想要的應用程式，按一下應用程式名稱以移至應用程式詳細資料頁面，然後選取 [ **許可權] 索引卷** 標。
1. 在 **Microsoft Graph資源特定同意 (RSC)** 許可權下，檢閱應用程式要求的 RSC 許可權。

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="應用程式 RSC 許可權的螢幕擷取畫面。":::

## <a name="known-issues"></a>已知的問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>某些要求許可權的協力廠商應用程式的 [許可權] 欄中不會顯示 [檢視詳細資料] 連結

目前，在 Azure AD 中註冊要求許可權的所有協力廠商應用程式都無法檢閱許可權和授與同意。 您會在 [許可權] 欄中看到[檢 **視詳細資料** ] 連結，而不是 [ **--** 檢視詳細 **資料]** 連結。 我們正與 ISV 合作，為其應用程式啟用此功能。

## <a name="related-topics"></a>相關主題

* [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
* [Microsoft 身分識別平臺端點中的許可權與同意](/azure/active-directory/develop/v2-permissions-and-consent)
* [Teams中的特定資源同意](resource-specific-consent.md)
* [RSC)  (資源特定同意 ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
*  (Ignite 2020 會話流覽[Teams應用程式生命週期](https://aka.ms/PR132)) 
