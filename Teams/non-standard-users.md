---
title: 不同使用者類型的 Teams 應用程式可用性和使用方式
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: kojika
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: 瞭解 Microsoft Teams 中的應用程式如何為來賓、同盟使用者和匿名使用者運作。
ms.localizationpriority: high
ms.date: 09/28/2022
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3511dec4f3238babc3356bafbe2bb69e791e7632
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131312"
---
# <a name="use-of-teams-apps-for-external-attendees-or-guest-from-outside-an-organization"></a>將 Teams 應用程式用於外部出席者或組織外部來賓

Teams 應用程式可讓您與組織外部人員共同作業。 身為系統管理員，您可以控制誰可以存取 Teams 聊天、會議和頻道，以便與貴組織的使用者共同作業。 如需詳細資訊，請參閱 [如何允許與外部出席者共同](manage-external-access.md) 作業 [，以及來賓可以在 Teams 中執行什麼動作](guest-access.md)。 本文著重于組織外部人員使用應用程式。

下列類型的使用者可以出現在 Teams 聊天或會議中，如果您允許，他們可以使用 Teams 中的應用程式。

* **來賓使用者** 是指非您組織員工、學生或成員的人。 他們沒有貴組織的學校或公司帳戶。

* **外部 (同盟) 使用者** 來自其他網域，且無法存取貴組織的 Teams 資源。

* **匿名使用者** 是透過連結加入會議的使用者。 使用者未使用其 Microsoft 帳戶或其組織的帳戶登入。

如需來賓與外部使用者之間的更詳細比較，請參閱 [與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。

## <a name="guests"></a>來賓

### <a name="install-update-and-delete-apps-for-guests"></a>為來賓安裝、更新和刪除應用程式

來賓無法在聊天、頻道或會議等共用內容中安裝、更新或刪除應用程式。 來賓可以在其個人範圍中使用訊息延伸模組和直接連結來執行此動作。 來賓無法從 Teams 傳統型應用程式存取 Teams 應用程式市集，但可以使用直接連結存取 Microsoft Store。

### <a name="usage-behavior-and-policy-for-guests"></a>來賓的使用行為和原則

如果應用程式是由組織的使用者安裝，來賓可以使用應用程式。

#### <a name="bots-installed-to-a-channel"></a>安裝到頻道的 Bot

來賓可以提及 Bot，並與介面卡互動。

#### <a name="personal-bots-installed-with-policies"></a>已安裝具有原則的個人 Bot

* 對於任何應用程式，來賓都遵守為主機組織設定的全域和整個組織許可權原則。 如果整個主機組織都已封鎖應用程式，則來賓也無法使用該應用程式。
* 也會為來賓安裝全域預設應用程式設定原則中包含的任何 Bot。
* 安裝 Bot 之後，Bot 和來賓可以主動互相溝通。
* 您無法從全域預設應用程式設定原則移除來賓。
* 若要避免來賓存取 Bot，您可以建立更多應用程式設定原則、將它們指派給內部使用者，以及使用自訂原則安裝 Bot。

## <a name="federated-users"></a>同盟使用者

### <a name="install-update-and-delete-apps-for-federated-users"></a>安裝、更新及刪除同盟使用者的應用程式

同盟使用者無法在任何內容中安裝、更新或刪除應用程式，例如個人、聊天、頻道或會議。 他們無法存取代管組織的 Teams App Store。

### <a name="usage-behavior-and-policy-for-federated-users"></a>同盟使用者的使用行為和原則

* 其他組織的人員遵守代管組織的全域 (預設) 原則
* 主機服務組織中的使用者可以在與其他組織的人員的會議聊天中新增應用程式。 來自其他組織的人員無法在會議聊天中新增應用程式，但一旦新增至聊天，即可與 Bot、索引標籤和訊息延伸模組互動。
* 在會議聊天中安裝 Bot 之後，它可以主動與該聊天中來自其他組織的人員通訊，而這些人員可以與 Bot 通訊。
* 系統會套用主機組織的資料原則。
* 會套用該使用者組織所共用之任何協力廠商應用程式的資料共用做法。

## <a name="anonymous-users"></a>匿名使用者

### <a name="install-update-and-delete-apps-for-anonymous-users"></a>安裝、更新及刪除匿名使用者的應用程式

匿名使用者無法在會議中安裝、更新或刪除應用程式。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名使用者的使用行為和原則

匿名使用者無法直接在會議中使用應用程式。 如果應用程式在聊天中傳送介面卡，匿名使用者就可以與卡片互動。 如果使用者層級的許可權原則啟用該應用程式，這類使用者就可以在 Teams 會議中與應用程式互動。 匿名使用者繼承使用者層級的全域預設許可權原則。

匿名使用者只能與會議中既有可用但無法取得及管理這類應用程式的應用程式互動。 即使匿名使用者正在參與會議，原生使用者仍可繼續使用會議應用程式。

### <a name="allow-anonymous-users-to-use-apps-in-meetings"></a>允許匿名使用者在會議中使用應用程式

根據預設，匿名使用者可以在會議中與現有的應用程式互動。 匿名使用者無法將新的應用程式新增至會議。 您可以不允許匿名使用者與應用程式互動。

1. 登入 Teams 系統管理中心並存取 **會議**  >  **[會議設定](https://admin.teams.microsoft.com/meetings/settings)**。

1. 在 [ **參與者**] 底下，將 **[匿名使用者可以在會議中與應用程式互動** ] 切換為 **[關閉]**。

1. 選取 [儲存 **]**。

## <a name="related-articles"></a>相關文章

* [允許匿名使用者加入會議](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。
* [在 Microsoft Teams 中管理應用程式設定原則](teams-app-setup-policies.md)。
* [如何允許與來賓和外部參與者共同作業](manage-external-access.md)。
* [來賓可以在 Teams 中做什麼](guest-access.md)
