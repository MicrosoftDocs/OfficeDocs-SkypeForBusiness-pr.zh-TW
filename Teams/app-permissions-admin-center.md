---
title: 在 Microsoft 團隊系統管理中心中查看應用程式許可權並授與系統管理員同意
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何查看 app 要求的許可權，以及如何在 Microsoft 團隊系統管理中心的 [管理應用程式] 頁面上，授與系統管理員的同意。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814607"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>在 Microsoft 團隊系統管理中心中查看應用程式許可權並授與系統管理員同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft [團隊系統管理中心] 中的 [ [管理應用程式](manage-apps.md) ] 頁面是您可在其中查看及管理組織的所有團隊應用程式的位置。 例如，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式至組織的 app 商店、封鎖或允許組織階層的應用程式，以及管理整個組織的應用程式設定。

您也可以在這裡，授與組織範圍的系統管理員同意要求存取資料許可權的 app，以及查看資源特定的同意 (RSC) 應用程式的許可權。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>授與整個組織的系統管理員同意應用程式

做為管理員，您可以查看並同意代表貴組織中所有使用者要求許可權的 app。 您這樣做是為了讓使用者在啟動 app 時，不需要查看並接受 app 要求的許可權。 此外，根據 Azure Active Directory (Azure AD) 中使用者的 [同意設定](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) 而定，部分使用者可能不允許取得存取公司資料之 app 的授權。

應用程式要求的許可權範例包括讀取儲存在小組中的資訊、讀取使用者的設定檔，以及代表使用者傳送電子郵件的能力。 若要深入瞭解，請參閱 [Microsoft 身分識別平臺端點中的許可權和同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。 

您必須是全域系統管理員，才能向 app 授與整個組織的同意。 [ **許可權** ] 欄會指出 app 是否擁有需要同意的許可權。 您會看到在 Azure AD 中註冊的每個應用程式的 [ **查看詳細資料** ] 連結，該 app 具有需要同意的許可權。 請記住，這只適用于自訂和協力廠商應用程式和。 您不會看到此連結，或需要為 Microsoft 發佈的 app 授與系統管理員的同意。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[管理應用程式] 頁面上 [許可權] 欄的螢幕擷取畫面":::

若要向 app 授與整個組織的同意，請依照下列步驟進行：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。
2. 執行下列其中一項動作：
    - 搜尋您要的應用程式，按一下應用程式名稱以移至 [應用程式詳細資料] 頁面，然後選取 [ **許可權** ] 索引標籤。
    - 以遞減順序排序 [ **許可權** ] 欄，以尋找應用程式，然後選取 [ **查看詳細資料**]。 這麼做會將您帶到 [應用程式詳細資料] 頁面的 [ **許可權** ] 索引標籤。

3. 在 [ **全組織許可權**] 底下，選取 [ **審查許可權和同意**]。 您必須是全域系統管理員才能執行此動作。 [團隊服務管理員] 無法使用此選項。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="App 之 [許可權] 索引標籤上組織範圍許可權的螢幕擷取畫面":::

4. 在 [ **許可權** ] 索引標籤上，查看 app 所要求的許可權。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="應用程式所要求之許可權的螢幕擷取畫面":::

    > [!IMPORTANT]
    > 向 app 授與整個組織的同意，就能讓 app 存取貴組織的資料。 在准許同意前，請仔細檢查 app 要求的許可權。
5. 如果您同意 app 要求的許可權，請按一下 [ **接受** ] 以授與同意。 橫幅會暫時出現在頁面頂端，讓您知道該 app 已授與要求的許可權。 App 現在可以存取貴組織中所有使用者的指定資源，且不會提示其他人查看許可權。

在您接受許可權之後，您會在 [應用程式詳細資料] 頁面上的 [ **全組織許可權** ] 下看到一則訊息，告知您已獲「同意」。 若要查看應用程式許可權的詳細資料，請按一下 **Azure Active Directory** 連結，移至 Azure AD 入口網站中的 app 頁面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="授與同意時所顯示之訊息的螢幕擷取畫面":::

如果您組織中的使用者可以授與同意，且如果一或多位使用者獲准同意某個特定的 app，您就只會看到訊息，告訴您同意已授與 Azure Active Directory 連結。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>查看應用程式的資源特定同意許可權

RSC 許可權讓小組擁有者同意 app 存取及修改小組資料的授權。 RSC 許可權是精確、團隊特有的許可權，可定義應用程式在特定團隊中的功能。 RSC 許可權的範例包括建立及刪除頻道、取得團隊設定，以及建立及移除頻道索引標籤的功能。 RSC 許可權是在應用程式資訊清單中定義，而不是在 Azure AD 中定義。

當您將應用程式新增至團隊時，您同意對 RSC 許可權的授權。 若要深入瞭解，請參閱小組中 (RSC) 與[資源特定同意的](resource-specific-consent.md)[資源特定同意](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

全域管理員和團隊服務系統管理員可以查看 RSC 許可權。 若要查看應用程式的 RSC 許可權，請依照下列步驟執行：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。
2. 搜尋您要的應用程式，按一下應用程式名稱以移至 [應用程式詳細資料] 頁面，然後選取 [ **許可權** ] 索引標籤。
3. 在 [ **Microsoft Graph 資源特定同意 (RSC) 許可權]** 下，查看 app 要求的 RSC 許可權。

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="應用程式的 RSC 許可權的螢幕擷取畫面":::

## <a name="related-topics"></a>相關主題

- [在 Microsoft 團隊系統管理中心管理您的應用程式](manage-apps.md)
- [Microsoft 身分識別平臺端點的許可權和同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [小組中的資源特定同意](resource-specific-consent.md)
- [ (RSC) 的資源特定同意 ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


