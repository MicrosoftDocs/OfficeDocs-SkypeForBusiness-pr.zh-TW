---
title: Teams非標準使用者的應用程式行為
author: SerdarSoysal
ms.author: serdars
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解應用程式中的應用程式Microsoft Teams非標準使用者的行為。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 621614b9fc3d46d4629ce8b62dbbcc7b579698db
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390825"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Microsoft Teams非標準使用者的應用程式行為

本文將說明當來賓Teams外部使用者、 (、) 使用者，以及匿名使用者時，Teams的行為。

- **來賓使用者** 不是貴組織的員工、學生或成員。 他們沒有貴組織的學校或公司帳戶。

- 外部 **(使用者**) 屬於另一個網域，且無法存取貴組織的小組或小組資源。

  > [!Note]
  > 有關來賓與外部使用者的詳細比較，請參閱與來自其他組織 [的使用者通訊](./communicate-with-users-from-other-organizations.md)。

- 匿名 **使用者** 是使用者透過連結加入Teams會議中的概念。 使用者尚未使用其 Microsoft 或組織帳戶登入。

## <a name="guest-users"></a>來賓使用者

### <a name="install-update-and-delete-for-guest-users"></a>為來賓使用者安裝、更新及刪除

來賓無法安裝、更新或刪除應用程式至共用內容 ，例如聊天、頻道或會議，但他們可以使用訊息擴充功能與直接連結來進入個人範圍。 來賓無法從桌面Teams存取 Teams應用程式市Teams，但可以使用直接連結存取。

### <a name="usage-behavior-and-policy-for-guest-users"></a>來賓使用者的使用行為與政策

如果應用程式是由原生使用者安裝，則來賓可以使用應用程式。

#### <a name="bots-installed-to-a-channel"></a>安裝至頻道的 Bot

Bot 可以主動訊息來賓使用者，但來賓無法與 Bot 互動。 來賓無法一對一訊息給 Bot、提及 Bot，或與與 Bot 通訊的介面卡片互動。

#### <a name="personal-bots-installed-with-policies"></a>使用策略安裝的個人 Bot

- 來賓會遵循針對任何應用程式的主機租使用者所設定之全域和全組織許可權原則。 如果整個主機組織的應用程式被封鎖，則來賓也無法使用此 App。
- 全域預設應用程式設定政策中包含的任何 Bot 也會為來賓安裝。
- 安裝 Bot 之後，Bot 可以主動與來賓通訊，而來賓可以與 Bot 重新通訊。
- 您無法從全域預設應用程式設定策略移除來賓。
- 若要避免來賓存取 Bot，您可以建立更多 App 設定策略、指派給內部使用者，以及使用自訂策略安裝 Bot。

## <a name="external-federated-users"></a>外部 (聯合) 使用者

### <a name="install-update-and-delete-for-external-users"></a>安裝、更新及刪除外部使用者

外部使用者無法在任何內容中安裝、更新或刪除應用程式，例如個人、聊天、頻道或會議。 他們無法存取主Teams應用程式存放區。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部使用者的使用行為與政策

- 來自其他組織的人遵守託管組織的全域 (全組織的預設) 原則
- 託管組織的使用者可以在與其他組織人員的會議聊天中新增應用程式。 來自其他組織的人無法在會議聊天中新增應用程式，但一旦新增到聊天中，就可以與 Bot、定位字元和訊息擴充功能互動。
- 在會議聊天中安裝 Bot 之後，它就可以主動與來自該聊天中的其他組織人員通訊，而且這些人員可以與 Bot 通訊。
- 會採用託管組織的資料原則，以及該使用者組織共用之任何協力廠商應用程式的資料共用作法。

## <a name="anonymous-users"></a>匿名使用者

### <a name="install-update-and-delete-for-anonymous-users"></a>為匿名使用者安裝、更新及刪除

匿名使用者無法安裝、更新或刪除會議中的應用程式。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名使用者的使用行為與政策

匿名使用者無法直接在會議中使用 App。 如果匿名使用者存在，原生使用者可以繼續使用會議應用程式。 如果應用程式在聊天中傳送介面卡片，匿名使用者可以與卡片互動。 若要詳細資訊，請參閱 [允許匿名使用者加入會議](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。

匿名使用者將繼承使用者層級全域預設權限原則。 如果使用者層級許可權Teams啟用應用程式，他們可以與會議中的應用程式互動。 匿名使用者只能與會議中現有的應用程式互動，而且無法取得和/或管理這些應用程式。

## <a name="related-topics"></a>相關主題

[管理應用程式中的應用程式設定Microsoft Teams](teams-app-setup-policies.md)
