---
title: 在系統管理中心中查看應用程式許可權並Microsoft Teams系統管理員同意
author: guptaashish
ms.author: guptaashish
ms.reviewer: vaibhava
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在系統管理中心的管理應用程式頁面上，查看應用程式要求的許可權，並授予Microsoft Teams同意。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54fbd67fffa666e7f07719305075be264f077976
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442269"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>在系統管理中心中查看應用程式許可權並Microsoft Teams系統管理員同意

系統[管理中心](manage-apps.md)中的Microsoft Teams頁面，就是您查看及管理組織Teams應用程式的地方。 例如，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式至組織的 App Store、封鎖或允許組織層級的應用程式，以及管理整個組織的應用程式設定。

在這裡，您也可以將全組織系統管理員同意授權給要求存取資料及查看資源特定許可權的應用程式， (RSC) 許可權。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>將全組織系統管理員同意授予應用程式

如果您是全域系統管理員，您可以為代表貴組織中所有使用者要求許可權的應用程式進行審查並授予同意。 如此一來，使用者就不需要在啟動 App 時，查看並接受應用程式要求的許可權。 此外，根據使用者在 Azure Active Directory (Azure AD) 中的同意[](/azure/active-directory/manage-apps/configure-user-consent)設定，某些使用者可能無法將同意授予存取公司資料的應用程式。

應用程式要求的許可權範例包括讀取儲存在小組的資訊、讀取使用者的設定檔，以及代表使用者傳送電子郵件。 若要深入瞭解，請參閱端點中的許可權[Microsoft 身分識別平臺同意](/azure/active-directory/develop/v2-permissions-and-consent)。

許可權 **欄** 會指出應用程式是否具有需要同意的許可權。 在具有需要 **同意許可權的** 應用程式中，您Azure AD註冊的每個應用程式，都會看到一個 View 詳細資料連結。 請記住，這僅適用于自訂和協力廠商應用程式。 您不會看到此連結，或需要針對 Microsoft 發佈的 App 授予系統管理員同意。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="管理應用程式頁面上的許可權欄螢幕擷取畫面。":::

若要將應用程式授予全組織同意，請遵循下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 執行下列其中一項：
    - 搜尋您想要的應用程式，按一下應用程式名稱以前往應用程式詳細資料頁面，然後選取 [ **許可權> 索引** 鍵。
    - 以遞 **減** 順序排序許可權欄以尋找應用程式，然後選取查看 **詳細資料**。 這麼做會帶您到 **應用程式詳細** 資料頁面的許可權選項卡。

3. 在 **全組織許可權下**，選取 **審查許可權和同意**。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="應用程式之許可權之全組織許可權的螢幕擷取畫面。":::

    您必須是全域系統管理員才能這麼做。 服務系統管理員無法Teams這個選項。

4. 在許可權 **選項卡** 上，查看應用程式要求的許可權。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="應用程式要求的許可權螢幕擷取畫面。":::

    > [!IMPORTANT]
    > 將整個組織同意授予應用程式，可讓應用程式存取貴組織的資料。 在您授予同意之前，請仔細查看應用程式要求的許可權。
5. 如果您同意應用程式要求的許可權， **請按一下 [接受** 以授予同意。 頁面頂端暫時會出現橫幅，讓您知道已針對應用程式授予要求的許可權。 應用程式現在可存取貴組織中所有使用者的指定資源，系統不會提示其他人檢查許可權。

接受許可權之後，您將在應用程式詳細資料頁面上的全組織許可權下看到一則訊息，讓您知道已授予同意。 若要查看應用程式許可權的詳細資訊，請按一下 [**Azure Active Directory連結，** 以前往應用程式入口網站中的Azure AD頁面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="已同意時顯示之訊息的螢幕擷取畫面。":::

如果貴組織中允許使用者授予同意，且有一或多個使用者已授予特定應用程式同意，您也會看到相同的訊息，讓您知道已授予同意，Azure AD 入口網站中的 Azure Active Directory 連結至應用程式頁面。

> [!NOTE]
> 雖然 Teams 服務系統管理員無法使用審查許可權和同意選項，且無法將整個組織系統管理員同意給應用程式，Teams 服務系統管理員可以針對應用程式在許可權選項卡上查看內容。**** 例如，Teams系統管理員可以按一下 [**Azure Active Directory連結，** 即可在 Azure AD 入口網站中Azure AD詳細資料。

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>查看應用程式的資源特定同意許可權

RSC 許可權允許團隊擁有者同意應用程式存取及修改小組的資料。 RSC 許可權是精細Teams特定許可權，可定義應用程式可在特定小組中執行哪些工作。 RSC 許可權的範例包括建立和刪除頻道、取得團隊的設定，以及建立和移除頻道標籤。

RSC 許可權在應用程式清單中定義，而不是在 Azure AD。 當您將應用程式新增到團隊時，即表示您同意 RSC 許可權。 若要深入瞭解，請參閱 [RSC (特定) ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

全域系統管理員Teams服務系統管理員可以在應用程式詳細資料頁面的許可權選項卡上，查看應用程式的 RSC 許可權。****

若要查看應用程式的 RSC 許可權，請遵循下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 搜尋您想要的應用程式，按一下應用程式名稱以前往應用程式詳細資料頁面，然後選取 [ **許可權> 索引** 鍵。
3. 在 **Microsoft Graph RSC (許可權**) ，請審查應用程式要求 RSC 許可權。

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="應用程式 RSC 許可權的螢幕擷取畫面。":::

## <a name="known-issues"></a>已知問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>部分要求許可權的協力廠商應用程式不會在許可權欄中顯示 「查看詳細資料」連結

目前，無法針對在要求許可權的應用程式中註冊的所有協力廠商應用程式Azure AD許可權和授權。 除了查看 **詳細資料** 連結外，您也會在許可權 **--** 欄中 **看到** 。 我們正在與 ISV 合作，為應用程式啟用此功能。

## <a name="related-topics"></a>相關主題

- [在系統管理中心管理Microsoft Teams應用程式](manage-apps.md)
- [端點中的許可權Microsoft 身分識別平臺同意](/azure/active-directory/develop/v2-permissions-and-consent)
- [中特定資源Teams](resource-specific-consent.md)
- [RSC (特定資源) ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [流覽 Teams App 生命週期 (](https://aka.ms/PR132)點 2020 會話) 
