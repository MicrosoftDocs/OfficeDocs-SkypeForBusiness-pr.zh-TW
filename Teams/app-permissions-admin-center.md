---
title: 在 Microsoft Teams 系統管理中心中查看應用程式許可權並授予系統管理員同意
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 系統管理中心的管理應用程式頁面上，查看應用程式要求的許可權，並授予應用程式系統管理員同意。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2833a548ccf66b327d9feb71155f1ed33a671f1c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094655"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心中查看應用程式許可權並授予系統管理員同意

Microsoft [Teams 系統](manage-apps.md) 管理中心的管理應用程式頁面就是您查看及管理貴組織所有 Teams 應用程式的地方。 例如，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式至組織的 App Store、封鎖或允許組織層級的應用程式，以及管理整個組織的 App 設定。

在這裡，您也可以將全組織系統管理員同意授權給要求存取資料的許可權，並針對應用程式的許可權來 (資源) 同意。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>將全組織系統管理員同意授予應用程式

如果您是全域系統管理員，您可以為代表貴組織中所有使用者要求許可權的應用程式進行審查並授予同意。 如此一來，使用者就不需要在啟動 App 時，查看並接受應用程式要求的許可權。 此外，根據 Azure Active [](/azure/active-directory/manage-apps/configure-user-consent) Directory (Azure AD) 中的使用者同意設定，某些使用者可能無法將同意授予存取公司資料的應用程式。

應用程式要求的許可權範例包括讀取儲存在小組的資訊、讀取使用者的設定檔，以及代表使用者傳送電子郵件。 若要深入瞭解，請參閱 Microsoft 身分識別平臺端點 [的許可權與同意](/azure/active-directory/develop/v2-permissions-and-consent)。 

許可權 **欄** 會指出應用程式是否有需要同意的許可權。 針對在 Azure  AD 中註冊並擁有需要同意的許可權的每個應用程式，您會看到一個 View 詳細資料連結。 請記住，這僅適用于自訂和協力廠商應用程式。 您不會看到此連結，或需要針對 Microsoft 發佈的 App 授予系統管理員同意。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="管理應用程式頁面上的許可權欄螢幕擷取畫面":::

若要將應用程式授予全組織同意，請遵循下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 執行下列其中一項：
    - 搜尋您想要的應用程式，按一下應用程式名稱以前往應用程式詳細資料頁面，然後選取 [ **許可權> 索引** 鍵。
    - 以遞 **減** 順序排序許可權欄以尋找應用程式，然後選取 View **Details**。 這麼做會帶您到 **應用程式詳細** 資料頁面的許可權選項卡。

3. 在 **全組織許可權下**，選取審查 **許可權和同意**。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="應用程式之許可權之全組織許可權的螢幕擷取畫面":::

    您必須是全域系統管理員才能這麼做。 Teams 服務系統管理員無法使用此選項。

4. 在許可權 **選項卡** 上，查看應用程式要求的許可權。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="應用程式要求的許可權螢幕擷取畫面":::

    > [!IMPORTANT]
    > 將整個組織同意授予應用程式，可讓應用程式存取貴組織的資料。 在您授予同意之前，請仔細查看應用程式要求的許可權。
5. 如果您同意應用程式要求的許可權，請按一下 **[接受** 以授予同意。 頁面頂端暫時會出現橫幅，讓您知道已針對應用程式授予要求的許可權。 應用程式現在可存取貴組織中所有使用者的指定資源，系統不會提示其他人檢查許可權。

接受許可權之後，您將在應用程式詳細資料頁面上的全組織許可權下看到一則訊息，讓您知道已授予同意。 若要查看應用程式許可權的詳細資訊，請按一下 **Azure Active Directory** 連結，以前往 Azure AD 入口網站中的應用程式頁面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="已同意時顯示之訊息的螢幕擷取畫面":::

如果貴組織中允許使用者授予同意，且有一或多個使用者已授予特定應用程式同意，您也會看到相同的訊息，讓您知道已授予同意，Azure Active Directory 連結會連結到 Azure AD 入口網站中的應用程式頁面。

> [!NOTE]
> 雖然 Teams服務系統管理員無法使用審查許可權和同意選項，且無法將整個組織系統管理員同意給應用程式，但 Teams 服務系統管理員可以在應用程式的許可權標籤上查看內容。  例如，Teams 服務系統管理員可以按一下 **Azure Active Directory** 連結，在 Azure AD 入口網站中查看應用程式許可權詳細資料。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>查看應用程式的資源特定同意許可權

RSC 許可權允許團隊擁有者同意應用程式存取及修改小組的資料。 RSC 許可權是精細的 Teams 特定許可權，可定義應用程式可在特定團隊中執行哪些工作。 RSC 許可權的範例包括建立和刪除頻道、取得團隊的設定，以及建立和移除頻道標籤。 

RSC 許可權在應用程式清單中定義，而不是在 Azure AD 中定義。 當您將應用程式新增到團隊時，即表示您同意 RSC 許可權。 若要深入瞭解，請參閱[RSC (特定) 。](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

全域系統管理員和 Teams 服務系統管理員可以在應用程式詳細資料頁面的許可權選項卡上，查看應用程式的 RSC 許可權。 

若要查看應用程式的 RSC 許可權，請遵循下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 搜尋您想要的應用程式，按一下應用程式名稱以前往應用程式詳細資料頁面，然後選取 [ **許可權> 索引** 鍵。
3. 在 **Microsoft Graph 資源特定同意 (RSC**) 許可權下，請審查應用程式要求 RSC 許可權。

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="應用程式 RSC 許可權的螢幕擷取畫面":::

## <a name="known-issues"></a>已知問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>部分要求許可權的協力廠商應用程式不會在許可權欄中顯示 「查看詳細資料」連結

目前，在 Azure AD 中註冊的所有要求許可權的協力廠商應用程式，無法審查許可權並授予同意。 除了查看 **詳細資料** 連結外，您也會在許可權欄中 **--** 看到。 我們正在與 ISV 合作，為應用程式啟用此功能。

## <a name="related-topics"></a>相關主題

- [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
- [Microsoft 身分識別平臺端點的許可權與同意](/azure/active-directory/develop/v2-permissions-and-consent)
- [Teams 中的特定資源同意](resource-specific-consent.md)
- [RSC (特定) ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [流覽 Teams 應用程式生命週期 (](https://aka.ms/PR132) 點 2020 會話) 