---
title: 根據使用者類型Teams應用程式行為
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解Microsoft Teams中的應用程式對於不同類型的使用者有何行為。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a407564986d5e4c758d39e2684e5c068539bb9dc
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922464"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>根據使用者類型Microsoft Teams應用程式行為

當來賓、外部 (同盟) 和匿名使用者在Teams內容中出現時，Teams應用程式的行為。

* **來賓使用者** 是指非您組織員工、學生或成員的人。 他們沒有貴組織的學校或公司帳戶。

* **外部 (同盟) 使用者** 屬於另一個網域，無法存取貴組織的小組或小組資源。

  > [!Note]
  > 如需來賓與外部使用者的更詳細比較， [請參閱與其他組織的使用者通訊](./communicate-with-users-from-other-organizations.md)。

* **匿名使用者** 是使用者透過連結加入會議Teams會議的概念。 使用者尚未使用其 Microsoft 或組織的帳戶登入。

## <a name="guest-users"></a>來賓使用者

### <a name="install-update-and-delete-for-guest-users"></a>為來賓使用者安裝、更新和刪除

來賓無法在聊天、頻道或會議等共用內容中安裝、更新或刪除應用程式，但可以使用訊息延伸模組和直接連結來進入其個人範圍。 來賓無法從Teams桌面應用程式存取Teams應用程式市集，但可以直接連結存取。

### <a name="usage-behavior-and-policy-for-guest-users"></a>來賓使用者的使用行為和原則

如果應用程式是由原生使用者安裝，來賓可以使用應用程式。

#### <a name="bots-installed-to-a-channel"></a>安裝到頻道的 Bot

來賓使用者可以提及 Bot，並與介面卡互動。

#### <a name="personal-bots-installed-with-policies"></a>已安裝具有原則的個人 Bot

* 來賓會遵守適用于任何應用程式之主機租使用者所設定的全域和整個組織許可權原則。 如果整個主機組織都已封鎖應用程式，則來賓也無法使用該應用程式。
* 也會為來賓安裝全域預設應用程式設定原則中包含的任何 Bot。
* 安裝 Bot 之後，Bot 可以主動與來賓通訊，來賓可以回復與 Bot 的通訊。
* 您無法從全域預設應用程式設定原則移除來賓。
* 若要避免來賓存取 Bot，您可以建立更多應用程式設定原則、將它們指派給內部使用者，以及使用自訂原則安裝 Bot。

## <a name="external-federated-users"></a>外部 (同盟) 使用者

### <a name="install-update-and-delete-for-external-users"></a>安裝、更新及刪除外部使用者

外部使用者無法在任何內容中安裝、更新或刪除應用程式，例如個人、聊天、頻道或會議。 他們無法存取代管組織的Teams應用程式市集。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部使用者的使用行為與原則

* 其他組織的人員遵守代管組織的全域 (預設) 原則
* 主機服務組織中的使用者可以在與其他組織的人員的會議聊天中新增應用程式。 其他組織的人員無法在會議聊天中新增應用程式，但一旦新增至聊天，就可以與 Bot、索引標籤和訊息延伸模組互動。
* 在會議聊天中安裝 Bot 之後，它可以主動與該聊天中來自其他組織的人員通訊，而這些人員可以與 Bot 通訊。
* 主機服務組織的資料原則，以及由該使用者組織共用的任何協力廠商應用程式的資料共用做法都會套用。

## <a name="anonymous-users"></a>匿名使用者

### <a name="install-update-and-delete-for-anonymous-users"></a>安裝、更新及刪除匿名使用者

匿名使用者無法在會議中安裝、更新或刪除應用程式。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名使用者的使用行為和原則

匿名使用者無法直接在會議中使用應用程式。 匿名使用者繼承使用者層級的全域預設許可權原則。 如果應用程式在聊天中傳送介面卡，匿名使用者就可以與卡片互動。 如果使用者層級的許可權原則啟用應用程式，這類使用者可以在Teams會議中與應用程式互動。

匿名使用者只能與會議中既有可用且無法取得及管理這類應用程式的應用程式互動。 即使匿名使用者正在參與會議，原生使用者仍可繼續使用會議應用程式。

## <a name="see-also"></a>另請參閱

* [允許匿名使用者加入會議](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。
* [在 Microsoft Teams 中管理應用程式設定原則](teams-app-setup-policies.md)。
