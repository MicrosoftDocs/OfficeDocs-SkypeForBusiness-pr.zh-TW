---
title: 管理自訂和側載的應用程式
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解什麼是 Microsoft Teams 中的自訂應用程式和側載應用程式，並管理應用程式以規範其行為、推行和許可權。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: d7c23b424db102b21e88944e2ab55d8a2fe98c08
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299293"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>瞭解及管理自訂及側載的應用程式

Microsoft Teams 可讓組織內部的開發人員為組織內部使用者建置、測試及部署自訂應用程式。 這類應用程式稱為自訂應用程式或商務營運應用程式。 貴組織可能會針對組織特定的需求委託建立自訂應用程式。

身為系統管理員的您有權為整個組織或特定使用者允許或封鎖這類應用程式。 貴組織的開發人員可以使用與 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 整合的 Teams 來建立自訂低程式碼解決方案。

開發人員可以透過 Teams 提交自訂應用程式，以取得系統管理員的核准。您可以使用應用程式設定原則來控制自訂應用程式的推出、發佈和許可權。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="螢幕擷取畫面顯示如何在全組織設定面板中允許貴組織中的自訂應用程式。" lightbox="media/custom-app-policy.png":::

允許使用自訂應用程式之後，使用者可以在 Teams 市集的左側導覽中選取 **[為您的組織打造** ] 來找到它。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 傳統型應用程式中 Teams 市集中自訂應用程式的螢幕擷取畫面。" lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>瞭解自訂應用程式側載

開發自訂應用程式時，以及在發佈這些應用程式給使用者之前，開發人員會透過將應用程式新增至 Teams 市集進行測試來測試應用程式。 開發人員可以自行或使用指定的使用者群組進行測試，但組織中的其他使用者無法透過 Microsoft Store 使用此應用程式。 此方法稱為側載應用程式，僅適用於自訂應用程式。

開發人員可以側載應用程式，將它提供給特定團隊的成員使用，通常是用來測試開發中的應用程式。 以這種方式使用應用程式會限制應用程式開發人員的使用，而且只要系統管理員允許在 Teams 中側載，就不需要系統管理員核准。

開發人員可以與特定團隊共用側載應用程式，而不需要將它提交到 Teams 應用程式目錄。 它讓側載的自訂應用程式可供少數使用者使用，但無法在貴組織的應用程式市集中提供給所有使用者。

身為系統管理員，您可以不允許所有開發人員側載應用程式。 如果您不允許側載，開發人員仍然可以透過[建立個別的測試租用戶](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)來測試其應用程式。 自訂應用程式開發完成後，開發人員會要求系統管理員將自訂應用程式發佈給使用者。 如需詳細資料，請參閱 [如何發佈自訂應用程式](/microsoftteams/upload-custom-apps)。 身為系統管理員，您可以允許或不允許特定使用者使用自訂應用程式。

## <a name="allow-developers-to-upload-custom-apps"></a>允許開發人員上傳自訂應用程式

您可以建立自訂原則或編輯全域原則，以根據組織的需求來允許或封鎖自訂應用程式。 若要建立可讓組織開發人員上傳自訂應用程式的自訂原則，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[設定原則](https://admin.teams.microsoft.com/policies/app-setup)**。

1. 選取 [新增 **]**。

1. 提供原則的名稱和描述。

1. 開啟或關閉 **[上傳自訂應用程式]**。

> [!NOTE]
> 若要變更此設定，請在租使用者的 [整個組織應用程式設定](manage-apps.md#manage-org-wide-app-settings)中允許協力廠商應用程式。

## <a name="related-articles"></a>相關文章

* [管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)
* [瞭解管理應用程式的原則](app-policies.md)
* [瞭解協力廠商應用程式](overview-third-party-apps.md)
