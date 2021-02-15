---
title: 適用于非標準使用者的 Teams 應用程式行為
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解 Microsoft Teams 中的應用程式對非標準使用者的行為。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 683ba9a20c51a23fa1468c07407a389c23dba507
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237494"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>適用于非標準使用者的 Microsoft Teams 應用程式行為

本文將說明當 Teams 環境中出現來賓、外部 (、) 和匿名使用者時，Teams 中的應用程式行為。

- 來賓 **使用者** 不是貴組織的員工、學生或成員。 他們沒有貴組織的學校或公司帳戶。

- 外部 **(使用者)** 屬於另一個網域，且無法存取貴組織的小組或小組資源。

>[!Note]
> 有關來賓與外部使用者的詳細比較， [請參閱與其他組織的使用者通訊](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)。

- 匿名 **使用者** 是 Teams 會議中使用者透過連結加入會議的概念。 使用者尚未使用其 Microsoft 或組織帳戶登入。

## <a name="guest-user-access"></a>來賓使用者存取權

### <a name="install-update-and-delete-for-guest-users"></a>為來賓使用者安裝、更新和刪除

來賓無法安裝、更新或刪除共用內容的應用程式，例如聊天、頻道或會議。 他們可以使用郵件延伸模組和直接連結，將應用程式安裝、更新或刪除到個人範圍。 來賓無法存取 Teams App Store。

### <a name="usage-behavior-and-policy-for-guest-users"></a>來賓使用者的使用行為與政策

如果應用程式是由原生使用者安裝，來賓可以使用應用程式。

Bot 可以主動訊息給來賓使用者，但來賓無法與 Bot 互動。 來賓無法以 1：1 訊息給 Bot、@ 提及 Bot，或與與 Bot 通訊的介面卡互動。

來賓將遵守針對任何應用程式的主機租使用者所設定之全域和全組織許可權原則。  (換句話說，如果整個主機組織都封鎖了應用程式，則來賓也因此無法使用此 App。) 

設定原則不適用於來賓使用者。 這表示系統管理員從預設政策釘寄的應用程式不會影響來賓使用者。

## <a name="external-federated-user-access"></a>外部 (伺服器) 使用者存取權

### <a name="install-update-and-delete-for-external-users"></a>安裝、更新及刪除外部使用者

外部使用者無法在任何內容中安裝、更新或刪除應用程式，例如個人、聊天、頻道或會議。 他們無法存取 Teams App Store。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部使用者的使用行為與政策

外部使用者無法使用任何 Teams 應用程式，而且當外部使用者新增到與原生使用者相關內容時，所有原生和外部使用者都無法再使用應用程式。

外部使用者不會受到應用程式政策的影響，因為他們無法使用 Teams 應用程式。

## <a name="anonymous-user-in-meetings-access"></a>會議存取中的匿名使用者

### <a name="install-update-and-delete-for-anonymous-users"></a>為匿名使用者安裝、更新和刪除

匿名使用者無法安裝、更新或刪除會議中的應用程式。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名使用者的使用行為與政策

匿名使用者無法直接在會議中使用應用程式。 如果匿名使用者存在，原生使用者可以繼續使用會議應用程式。 如果應用程式在聊天中傳送自適性卡片，匿名使用者可以與卡片互動。

匿名使用者將繼承使用者層級的全域預設權限原則。 此控制項可讓匿名使用者與 Teams 會議中的應用程式互動，只要使用者層級的權限原則已啟用應用程式。 匿名使用者只能與已在會議使用的應用程式互動，而且無法取得及/或管理這些應用程式。
