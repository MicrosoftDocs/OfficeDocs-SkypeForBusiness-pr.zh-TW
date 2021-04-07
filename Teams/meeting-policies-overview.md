---
title: 管理會議原則
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: 瞭解如何在 Teams 中管理會議策略設定，並使用這些設定來控制提供給會議參與者的功能，供使用者排程的會議使用。
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598708"
---
# <a name="manage-meeting-policies-in-teams"></a>管理 Teams 中的會議原則

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。 您可以使用全域 (全組織的預設) 自動建立或建立及指派自訂策略。 您可以在 Microsoft Teams 系統管理中心或使用 [PowerShell 管理會議政策](teams-powershell-overview.md)。

> [!NOTE]
> 有關使用角色管理會議簡報者和出席者許可權的資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

您可以用下列方式執行策略，這會影響會議開始前、會議期間或會議後使用者的會議體驗。

|實現類型  |描述  |
|---------|---------|
|每個召集人    |當您執行每個召集人的政策時，所有會議參與者會繼承召集人的政策。 例如， **自動** 准許人員是每個召集人的政策，並控制使用者是否直接加入會議，或是在大廳等候指派該政策的使用者排程的會議。          |
|每個使用者    |當您執行每個使用者原則時，只會使用每個使用者原則來限制召集人和/或會議參與者的某些功能。 例如， **在頻道中允許現在開會** 是每個使用者的政策。     |
|每個召集人和每個使用者     |當您將每個召集人和每個使用者策略組合在一起時，根據會議參與者的政策和召集人的政策，某些功能會受到限制。 例如， **允許雲端錄製** 是每個召集人和每個使用者的政策。 開啟此設定，讓會議召集人和參與者開始和停止錄製。

您可以編輯全域原則中的設定，或建立並指派一或多個自訂策略。 除非您建立並指派自訂策略，否則使用者將取得全域原則。

> [!NOTE]
> 如果使用者已啟用音訊會議授權，或使用者允許進行音訊會議，則會議詳細資料將不可用，則會議詳細資料將可以使用。

## <a name="create-a-custom-meeting-policy"></a>建立自訂會議策略

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **會議**  >  **會議政策**。
2. 按一下 [新增 **]**。
3. 輸入原則的名稱和描述。 名稱不能包含特殊字元，且長度不可超過 64 個字元。
4. 選擇您想要的設定。
5. 按一下 [儲存]。

例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。 您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：

在 [音訊與視訊] 下：

- 關閉 [允許雲端錄製]。
- 關閉 [允許 IP 視訊]。

在 [內容共用] 下：

- 停用 [螢幕畫面分享模式]。
- 關閉 [允許白板]。
- 關閉 [允許共用記事]。

然後，將原則指派給使用者。

## <a name="edit-a-meeting-policy"></a>編輯會議政策

您可以編輯全域原則和您建立的任何自訂策略。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **會議**  >  **會議政策**。
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 從此處，進行您需要的變更。
4. 按一下 [儲存]。

> [!NOTE]
> 一次只能指派一個會議策略給使用者。

## <a name="assign-a-meeting-policy-to-users"></a>將會議原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> 如果使用者已指派給使用者，則無法刪除該策略。 您必須先指派不同的策略給所有受影響的使用者，然後您可以刪除原始策略。

## <a name="meeting-policy-settings"></a>會議策略設定

當您在會議政策頁面上選取現有的策略或 **選取新增以** 新增策略時，您可以設定下列設定。

- [一般](meeting-policies-in-teams-general.md)
- [音訊&影片](meeting-policies-audio-and-video.md)
- [內容共用](meeting-policies-content-sharing.md)
- [參與者&來賓](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](assign-policies.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議政策](meeting-policies-restricted-anonymous-access.md)