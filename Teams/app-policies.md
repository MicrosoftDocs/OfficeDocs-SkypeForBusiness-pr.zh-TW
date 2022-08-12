---
title: 在 Teams 中管理應用程式的應用程式原則概觀
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
search.appverid: ''
description: 了解在 Microsoft Teams 中，用來管理應用程式的應用程式權限原則、應用程式設定原則和自訂應用程式原則。
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 5a377923412ad1835e4a0a3c099d31adf283267b
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299032"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>用來管理應用程式存取權的應用程式原則概觀

Microsoft Teams 使用原則來管理存取和安裝行為。 原則可協助 Teams 系統管理員控制下列應用程式行為：

* 在細微層級設定使用者的應用程式存取權。 它可協助每個使用者僅使用系統管理員對其允許的應用程式。

* 為特定使用者釘選相關應用程式。 它可協助使用者輕鬆開始使用，並快速存取相關應用程式，因為已釘選的應用程式無需介入即可自動安裝。

## <a name="app-permission-policies"></a>應用程式權限原則

使用應用程式權限原則，Teams 系統管理員可以控制哪些應用程式可供其組織中的特定使用者使用。 您可以定義應用程式與使用者之間的確切存取對應，或兩者的任何組合。 例如，您可以為所有使用者允許一些應用程式、為特定使用者群組允許一些應用程式，或為特定使用者允許特定應用程式。

應用程式權限原則適用 Teams 中所有可用的應用程式類型。 例如，您可以使用應用程式權限原則，逐步推出第三方應用程式或自訂應用程式，方法是為特定使用者允許它。

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="應用程式權限原則的螢幕擷取畫面。" lightbox="media/app-permission-policy.png":::

若要深入了解，請參閱[如何管理自訂應用程式原則和設定](teams-app-permission-policies.md)。

## <a name="app-setup-policies"></a>應用程式設定原則

應用程式設定原則可讓您自訂使用者的應用程式體驗。 您會選擇要釘選到 Teams 用戶端中的應用程式列的應用程式，以及應用程式在網頁、桌面和行動用戶端上顯示的順序。

以下是如何使用應用程式設定原則的一些範例：

* 為使用者在其個人 Teams 環境中安裝應用程式。 它可協助推動認知和採用所需的應用程式。 例如，為人力資源團隊的成員釘選自訂招募和人才管理應用程式。
* 選擇性地釘選核心應用程式，例如聊天、Teams 和通話。

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Microsoft Teams 系統管理中心的應用程式設定原則螢幕擷取畫面。" lightbox="media/app-setup-policy.png":::

若要進一步了解，請參閱[如何管理應用程式設定原則](teams-app-setup-policies.md)。

## <a name="custom-app-policies"></a>自訂應用程式原則

Teams 可讓組織內的開發人員為組織的內部使用者建置、測試及部署自訂應用程式。 開發人員可以透過 Teams 提交其自訂應用程式，以獲得 Teams 系統管理員的核准。 您可以使用應用程式設定原則來控制組織中誰可以上傳自訂應用程式。 系統管理員可以使用全組織應用程式設定，允許其組織的使用者使用自訂應用程式和開發人員上傳自訂應用程式。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="顯示如何在全組織設定面板中允許組織中的自訂應用程式的螢幕擷取畫面。" lightbox="media/custom-app-policy.png":::

若要進一步了解，請參閱[如何管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。

## <a name="related-articles"></a>相關文章

* [使用原則管理 Teams](manage-teams-with-policies.md)
