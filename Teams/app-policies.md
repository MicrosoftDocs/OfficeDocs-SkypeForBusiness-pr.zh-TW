---
title: 在 Teams 中管理應用程式的應用程式原則概觀
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/25/2022
search.appverid: ''
description: 瞭解 Microsoft Teams 中用來管理應用程式的應用程式許可權原則和設定原則。
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1c99cd9c0be3251a237b547cd8a2096d2d0e02af
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494646"
---
# <a name="app-policies-used-to-manage-access-to-and-installation-of-apps"></a>用來管理應用程式存取和安裝的應用程式原則

Microsoft Teams 會使用應用程式原則來管理應用程式的存取和安裝行為。 應用程式原則可協助 Teams 系統管理員控制下列應用程式行為：

* 設定每個個別使用者或一組使用者的應用程式存取權。 它可協助系統管理員控制允許每個使用者使用的應用程式。

* 將這些應用程式釘選給與貴組織需求相關的使用者。 此外，系統管理員可以為使用者安裝應用程式，而不需要使用者介入。 它可協助使用者輕鬆開始使用相關的應用程式。

* 控制貴組織中的哪些開發人員可以提交自訂應用程式以供系統管理員核准。 它可協助您控制自訂應用程式上傳功能的存取權。

## <a name="app-permission-policies"></a>應用程式權限原則

透過應用程式許可權原則，Teams 系統管理員可控制組織中每個使用者可使用的應用程式。 您可以為所有使用者允許一些應用程式、允許特定使用者群組使用一些應用程式，或是允許特定使用者使用特定應用程式。 應用程式許可權原則與整個組織設定同時運作，並允許或封鎖每個個別應用程式的狀態。

應用程式許可權原則會套用至 [Teams 中所有可用的應用程式類型](deploy-apps-microsoft-teams-landing-page.md)。 使用應用程式許可權原則的一些範例案例為：

* 一開始會逐步將應用程式推出給部分使用者，並最終推出給所有使用者。
* 僅允許您人力資源部門成員的自訂註冊和人才管理應用程式，並為所有其他組織使用者封鎖它。

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="應用程式權限原則的螢幕擷取畫面。" lightbox="media/app-permission-policy.png":::

若要深入瞭解，請參閱 [如何管理應用程式許可權原則](teams-app-permission-policies.md)。

## <a name="app-setup-policies"></a>應用程式設定原則

應用程式設定原則可讓您設定 Teams 用戶端中使用者可使用應用程式的方式和位置。 您可以選擇要釘選到 Teams 用戶端中應用程式行的應用程式，並定義應用程式的顯示順序。

釘選或安裝應用程式有助於提高貴組織中所需應用程式的認知與採用。 變更會套用至 Web、桌面和行動裝置 Teams 用戶端。

使用應用程式設定原則的一些範例案例如下：

* 為您的人力資源小組成員釘選自訂的註冊和人才管理應用程式。
* 變更貴組織使用者預先釘選核心應用程式的順序。

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Microsoft Teams 系統管理中心的應用程式設定原則螢幕擷取畫面。" lightbox="media/app-setup-policy.png":::

若要進一步了解，請參閱[如何管理應用程式設定原則](teams-app-setup-policies.md)。

### <a name="option-to-upload-custom-apps"></a>上傳自訂應用程式的選項

貴組織可能會針對組織特定的需求委託建立自訂應用程式。 貴組織中的開發人員可以為組織內部的 Teams 使用者建置、測試及部署自訂應用程式。 您可以使用應用程式設定原則來控制組織中的誰可以上傳自訂應用程式。 您可以使用整個組織設定，讓使用者使用自訂應用程式。 您可以使用許可權原則，只允許特定的使用者使用自訂應用程式。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="顯示如何在全組織設定面板中允許組織中的自訂應用程式的螢幕擷取畫面。" lightbox="media/custom-app-policy.png":::

若要深入瞭解，請參閱 [如何管理自訂應用程式的原則和設定](teams-custom-app-policies-and-settings.md)。

## <a name="related-articles"></a>相關文章

* [使用原則管理 Teams](manage-teams-with-policies.md)
* [管理應用程式權限原則](teams-app-permission-policies.md)
* [管理應用程式設定原則](teams-app-setup-policies.md)
* [管理自訂應用程式的原則和設定](teams-custom-app-policies-and-settings.md)
