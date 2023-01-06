---
title: 在 Microsoft Teams 系統管理中心中檢視應用程式權限並授與系統管理員同意
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 08/17/2022
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 系統管理中心的 [管理應用程式] 頁面上，檢視應用程式要求的權限，以及將系統管理員同意授與應用程式。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f47755a668516b505c4ff4dd0f54bf9e8a919c8
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727775"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-teams-admin-center"></a>在 Teams 系統管理中心檢視應用程式許可權並授與系統管理員同意

系統管理員可從 Teams 系統管理中心的 [管理應用程式] 頁面檢視及管理所有 Teams 應用程式。 您可以管理在組織內建立且僅供使用者使用的自訂應用程式，以及管理 Teams App 市集中提供的協力廠商。 例如，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式至貴組織的 App 市集、允許組織層級或個別使用者的應用程式。

您也可以在這裡將整個組織的系統管理員同意授與應用程式，以為應用程式要求存取資料的權限，及檢視資源特定同意 (RSC)的權限。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>將全組織的系統管理員同意授與應用程式

如果您是全域系統管理員，您可以檢閱並同意代表貴組織中所有使用者要求許可權的應用程式。 如此一來，使用者就不必在啟動應用程式時，檢閱並接受應用程式要求的權限。 此外，根據 Azure Active Directory (Azure AD) 中的使用者[同意設定](/azure/active-directory/manage-apps/configure-user-consent)，某些使用者可能不受允許將同意授與存取公司資料的應用程式。

應用程式要求的權限範例包括讀取儲存在小組中的資訊、讀取使用者的設定檔，以及代表使用者傳送電子郵件的功能。 若要深入了解，請參閱 [Microsoft 身分識別平台端點中的權限與同意](/azure/active-directory/develop/v2-permissions-and-consent)。

**[權限]** 欄位會指出應用程式是否有需要同意的權限。 您會看到在 Azure AD 中註冊的有需要同意權限的每個應用程式的 **[檢視詳細資料]** 連結。 請記住，這僅適用於自訂和協力廠商應用程式。 此連結不適用於 Microsoft 提供的應用程式。 此外，系統管理員不需要針對這類應用程式授與同意。

若要授與應用程式全組織同意，請執行以下步驟：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **[Teams 應用程式]** > **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)**.。

1. 執行下列其中一項：
    * 搜尋您想要的應用程式，選取應用程式名稱以移至應用程式詳細資料頁面，然後選取 [ **許可權] 索引卷** 標。
    * 依遞減順序對 **[權限]** 欄位進行排序以尋找應用程式，然後選取 **[檢視詳細資料]**。 執行此工作將進入應用程式詳細資料頁的 **[權限]** 索引標籤。

1. 在 **[全組織權限]** 下，選取 **[檢閲權限和同意]**。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="應用程式 [權限] 索引標籤上全組織權限的螢幕擷取畫面。":::

    您必須是全域系統管理員才能執行此動作。 此選項不適用於 Teams 服務系統管理員。

1. 在 **[權限]** 索引標籤上，檢閲應用程式要求的權限。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="應用程式要求權限的螢幕擷取畫面。":::

    > [!IMPORTANT]
    > 將全組織同意授與應用程式，讓應用程式存取您組織的資料。 在您授與同意之前，請仔細檢閱應用程式要求的權限。

1. 如果您同意應用程式要求的許可權，請選取 [ **接受** ] 以授與同意。 頁面頂部會暫時顯示橫幅，告知您已為應用程式授與要求的權限。 應用程式現在可以存取貴組織中所有使用者的指定資源，並且不會提示其他人檢閲權限。

接受權限後，您將在應用程式詳細資料頁面上的 **[全組織權限]** 下看到告知已授與同意的訊息。 若要檢視應用程式許可權的詳細資料，請選取 **Azure Active Directory** 連結，以移至 Azure AD 入口網站中的應用程式頁面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="授與同意時顯示訊息的螢幕擷取畫面。":::

如果允許貴組織中的使用者授與同意，而且如果有一或多個使用者授與同意給特定應用程式，您也會看到相同的訊息，讓您知道已授與同意，以及 Azure AD 入口網站中應用程式頁面的 Azure Active Directory 連結。

> [!NOTE]
> 雖然 Teams 服務管理員無法使用 **[檢閱權限與同意]** 選項，而且他們無法將全組織的系統管理員同意授與應用程式，但 Teams 服務系統管理員可以在應用程式的 **[權限]** 索引標籤上檢視內容。 例如，Teams 服務系統管理員可以按一下 **Azure Active Directory** 連結，在 Azure AD 入口網站中檢視應用程式權限詳細資料。

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>檢視應用程式的資源特定同意權限

RSC 權限可讓團隊擁有者授與應用程式同意以存取及修改團隊資料。 RSC 權限是精細的 Teams 特定團隊，可定義應用程式在特定團隊中能執行的動作。 RSC 權限的範例包括建立和刪除頻道、取得團隊的設定，以及建立和移除頻道索引標籤的功能。

RSC 權限是在應用程式資訊清單中定義，而不是在 Azure AD 中定義。 當您將應用程式新增至團隊時，即表示同意 RSC 權限。 若要深入了解，請參閱 [資源特定同意 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

全域系統管理員和 Teams 服務系統管理員可以在應用程式詳細資料頁面的 **[權限]** 索引標籤上，檢視應用程式的 RSC 權限。

若要檢視應用程式的 RSC 權限，請遵循下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
1. 搜尋您想要的應用程式，選取應用程式名稱以移至應用程式詳細資料頁面，然後選取 [ **許可權] 索引卷** 標。
1. 在 **[Microsoft Graph 資源特定同意 (RSC) 權限]** 下，檢閱應用程式要求的 RSC 權限。

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="應用程式 RSC 權限的螢幕擷取畫面。":::

## <a name="known-issues"></a>已知的問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>有些要求權限的協力廠商應用程式的 [權限] 欄位中不會顯示 [檢視詳細資料] 連結

並非所有協力廠商應用程式都具有檢閱權限和授與同意的能力。 通常，當應用程式要求權限時，協力廠商應用程式在 Azure Active Directory 中註冊。 您會在 [權限] 欄位中看到 **`--`**，而不是 **[檢視詳細資料]** 連結。

## <a name="related-articles"></a>相關文章

* [瞭解 Azure AD 中的使用者與系統管理員同意](/azure/active-directory/manage-apps/user-admin-consent-overview)
* [Microsoft 身分識別平台端點中的權限與同意](/azure/active-directory/develop/v2-permissions-and-consent)
* [Teams 中的資源特定同意](resource-specific-consent.md)
* [資源特定同意 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [瀏覽 Teams 應用程式生命週期](https://aka.ms/PR132) (Ignite 2020 工作階段)
