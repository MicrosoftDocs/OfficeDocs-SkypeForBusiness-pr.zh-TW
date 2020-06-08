---
title: Teams 即時活動中的簡報者和參與者功能
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Teams 即時活動中的簡報者和參與者功能。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 7714442be770420797df1c51a532f769eb0350a4
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565856"
---
<a name="presenter-and-participant-capabilities-in-a-teams-live-event"></a>Teams 即時活動中的簡報者和參與者功能
======================================================

Microsoft Teams 即時活動支援許多參與者類型。 參與者可以根據他們在組織內部或外部的角色，存取各種即時活動功能。

可用的會議功能如下：

- 聊天 (包含相片和貼圖)
- 會議記錄
- 白板
- 錄製
- 檔案

本文將說明這些參與者功能，以及他們對即時活動功能所擁有的存取權。

## <a name="presenters-and-organizers"></a>簡報者和召集人

簡報者和召集人包括下列：

- 來自我的組織的簡報者
- 來自其他組織的使用者。 簡報者由召集人所指定，且需要來自召集人的個人邀請。

簡報者和召集人可以存取即時活動中的每一項功能。

## <a name="participants"></a>參與者

即時活動參與者有以下幾種類型：

- [租用戶內的參與者](#in-tenant-participant)
- [來賓參與者](#guest-participant)
- [外部 (同盟) 參與者](#external-federated-participant)
- [匿名參與者](#anonymous-participant)

### <a name="in-tenant-participant"></a>租用戶內的參與者

租用戶內的參與者屬於組織，並擁有租用戶的認證。 若要深入了解這類參與者，請參閱[安全性和 Microsoft Teams](teams-security-guide.md#participant-types)。

| 即時活動 |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **功能**       | 會議前 | 會議中 | 會議後 |
| 聊天 | N/A | N/A | 不適用 |
| 會議記錄 | 是 | 是 |是 |
| 白板 | 是 | 是 |是 |
| 錄製 | 不適用 |是 | 是 |
| 檔案 | 是 | 是 | 是 |
|||||||


### <a name="guest-participant"></a>來賓參與者

來賓參與者是來自其他組織的人員，該人員已受邀可存取您組織租用戶 (採用 Azure Active Directory B2B 平台) 中的 Teams 或其他資源。 可邀請來賓使用者加入一般會議和頻道會議。 如需來賓參與者的詳細資訊，請參閱[來賓體驗的方式](guest-experience.md#comparison-of-team-member-and-guest-capabilities) (部分機器翻譯)。

| 即時活動  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **功能**        | 會議前 | 會議中 | 會議後 |
| 聊天 | N/A | N/A | 不適用 |
| 會議記錄 | 是 | 是 | 是 |
| 白板 | 否 | 否 | 否 |
| 錄製 | 不適用 | 否 | 否 |
| 檔案 | 否 | 否 | 否 |
|||||||


### <a name="external-federated-participant"></a>外部 (同盟) 參與者

外部參與者在其他組織中使用 Teams 的人員，其受邀加入會議，因此無法存取貴組織的其他共用資源。 在會議名單上，外部使用者參與者會以自己本身組織中的相同身分識別名稱顯示。 若要深入了解外部參與者，請參閱[與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md#external-access)。

| 即時活動 |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **功能**         | 會議前 | 會議中 | 會議後 |
| 聊天 | N/A| N/A | 不適用 |
| 會議記錄 | 否 | 否 | 否 |
| 白板 | 否| 否 | 否 |
| 錄製 | 不適用 | 否 | 否 |
| 檔案 | 是 | 是 | 是 |
|||||||

### <a name="anonymous-participant"></a>匿名參與者

匿名參與者就像外部使用者，但他們的身分識別不會顯在會議中。 加入時，他們需手動輸入暱稱。 若要深入了解匿名參與者，請參閱[安全性和 Microsoft Teams](teams-security-guide.md#participant-types)。

| 即時活動|  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **功能**        | 會議前 | 會議中 | 會議後 |
| 聊天 | N/A | N/A | 不適用 |
| 會議記錄 | 不適用 | 否 | 不適用 |
| 白板 | N/A | N/A | 不適用 |
| 錄製 | 不適用 | 否 | 不適用 |
| 檔案 | 不適用 | 否 | 不適用 |
|||||||


## <a name="related-topics"></a>相關主題

[安全性和 Microsoft Teams](teams-security-guide.md)

[Teams 中的來賓存取](guest-access.md)

[Teams 的即時活動計畫 ](teams-live-events/plan-for-teams-live-events.md)
