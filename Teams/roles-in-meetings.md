---
title: Teams 會議中的簡報者和參與者功能
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
description: 了解 Teams 會議中的簡報者和參與者功能。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 11c5858532ade4fd4ed00f7c8f6d1d0c94baeb2d
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321732"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Teams 會議中的簡報者和參與者功能
======================================================

Microsoft Teams 會議支援許多參與者類型。 參與者可以根據他們在組織內部或外部的角色，存取各種會議功能。

可用的會議功能如下：

- 聊天 (包含相片和貼圖)
- 會議記錄
- 白板
- 錄製
- 檔案
- 排程會議 (僅適用於會議)

本文將說明這些參與者功能，以及他們對會議功能所擁有的存取權。

## <a name="presenters-and-organizers"></a>簡報者和召集人

簡報者和召集人包括下列：

- 來自我的組織的簡報者
- 來自其他組織的簡報者 - 包括匿名和外部參與者。 簡報者由召集人所指定，且需要來自召集人的個人邀請。

簡報者和召集人可以存取會議或即時活動中的每一項功能。

## <a name="participants"></a>參與者

會議參與者有以下幾種類型：

- [租用戶內的參與者](#in-tenant-participant)
- [來賓參與者](#guest-participant)
- [外部 (同盟) 參與者](#external-federated-participant)
- [匿名參與者](#anonymous-participant)

### <a name="in-tenant-participant"></a>租用戶內的參與者

租用戶內的參與者屬於組織，並擁有租用戶的認證。 若要深入了解這類參與者，請參閱[安全性和 Microsoft Teams](teams-security-guide.md#participant-types)。

|會議  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **功能**        | 會議前 | 會議中 | 會議後 |
| 聊天 | 是 | 是 | 是 |
| 會議記錄 | 是 | 是 |是 |
| 白板 | 是 | 是 |是 |
| 錄製 | 不適用 |是 | 是 |
| 檔案 | 是 | 是 | 是 |
| 排程會議 | 是 | 不適用 | 不適用 |
|||||||

### <a name="guest-participant"></a>來賓參與者

來賓參與者是來自其他組織的人員，該人員已受邀可存取您組織租用戶 (採用 Azure Active Directory B2B 平台) 中的 Teams 或其他資源。 可邀請來賓使用者加入一般會議和頻道會議。 如需來賓參與者的詳細資訊，請參閱[來賓體驗的方式](guest-experience.md#comparison-of-team-member-and-guest-capabilities) (部分機器翻譯)。

| 會議 |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **功能**        | 會議前 | 會議中 | 會議後 |
| 聊天 | 是 | 是 | 是 |
| 會議記錄 | 是 | 是 | 是 |
| 白板 | 否 | 否 |否 |
| 錄製 | 不適用 |否 | 否 |
| 檔案 | 是 | 是 | 是 |
| 排程會議 | 否 | N/A | 不適用 |
|||||||

### <a name="external-federated-participant"></a>外部 (同盟) 參與者

外部參與者在其他組織中使用 Teams 的人員，其受邀加入會議，因此無法存取貴組織的其他共用資源。 在會議名單上，外部使用者參與者會以自己本身組織中的相同身分識別名稱顯示。 若要深入了解外部參與者，請參閱[與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md#external-access)。

| 會議 (只能以來賓身分新增至團隊) ||
|-|-|-|
| **功能** |||
| 聊天 | 不適用 |
| 會議記錄 | 不適用 |  
| 白板 | 不適用 |
| 錄製 | 不適用 |  
| 檔案 | 不適用 |
| 排程會議 | 不適用 |
|||

### <a name="anonymous-participant"></a>匿名參與者

匿名參與者就像外部使用者，但他們的身分識別不會顯在會議中。 加入時，他們需手動輸入暱稱。 若要深入了解匿名參與者，請參閱[安全性和 Microsoft Teams](teams-security-guide.md#participant-types)。

| 會議  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **功能**        | 會議前 | 會議中 | 會議後 |
| 聊天 | 不適用 | 否 | 不適用 |
| 會議記錄 | 不適用 | 否 | 不適用 |
| 白板 | 不適用 | 否 | 不適用 |
| 錄製 | 不適用 | 否 | 不適用 |
| 檔案 | 不適用 | 否 | 不適用 |
| 排程會議 | 不適用 | N/A | 不適用 |
|||||||

## <a name="related-topics"></a>相關主題

[安全性和 Microsoft Teams](teams-security-guide.md)

[Teams 中的來賓存取](guest-access.md)
