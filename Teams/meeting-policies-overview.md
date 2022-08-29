---
title: 在 Microsoft Teams 中管理會議原則
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
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
description: 瞭解如何在 Teams 中管理會議原則設定，並使用這些設定來控制使用者排定之會議參與者可用的功能。
ms.openlocfilehash: 99c84f6c0dfcbd20824a90af49739eace200ecd2
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396544"
---
# <a name="manage-meeting-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理會議原則

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。 您可以使用自動建立的全域 (全組織預設值) 原則，或建立並指派自訂原則。 您可以在 Microsoft Teams 系統管理中心或使用 [PowerShell](teams-powershell-overview.md) 來管理會議原則。

> [!NOTE]
> 如需使用角色來管理會議簡報者和出席者權限的詳細資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

您可以以下列方式來實作原則，這會影響使用者在會議開始、會議期間或會議後的會議體驗。

|實作類型  |描述  |
|---------|---------|
|每一召集人    |當您實作每一召集人原則時，所有會議參與者都會繼承召集人的原則。 例如， **自動准許人員** 為每個召集人的原則，並控制使用者是否直接加入會議，或是在大廳等候被指派原則的使用者排程的會議。          |
|每一使用者    |當您實作每一使用者原則時，僅會套用每一使用者原則，以限制召集人和/或會議參與者的某些功能。 例如，在 **頻道中立即開會** 是個別使用者的原則。     |
|每一召集人和每一使用者     |當您實作每一召集人和每一使用者的原則組合時，系統會根據參與者的原則和召集人的原則，限制會議參與者的某些功能。 例如， **雲端錄製** 是每個召集人和個別使用者的原則。 開啟此設定可讓會議召集人和參與者開始和停止錄製。

您可以編輯全域原則中的設定，或建立並指派一或多個自訂原則。 除非您建立並指派自訂原則，否則使用者將會取得全域原則。

> [!NOTE]
> 如果使用者已啟用音訊會議授權，或使用者已獲允許進行音訊會議，則 [會議詳細資料] 按鈕將可供使用，否則會議詳細資料將無法使用。

## <a name="create-a-custom-meeting-policy"></a>建立自訂會議原則

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [會議 **]**  >  [會議原則 **]**。
2. 按一下 [新增 **]**。
3. 輸入原則的名稱和描述。 名稱不能包含特殊字元，且長度不可超過 64 個字元。
4. 選擇您想要的設定。
5. 按一下 [儲存]。

例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。 您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：

在 [音訊與視訊] 下：

- 關閉雲端錄製。
- 關閉 IP 視訊。

在 [內容共用] 下：

- 停用 [螢幕畫面分享模式]。
- 關閉 Whiteboard。
- 關閉 [共用記事]。

然後，將原則指派給使用者。

這段影片將示範建立自訂會議原則並指派給使用者 (或使用者) 的步驟。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53Wv0?autoplay=false]

## <a name="edit-a-meeting-policy"></a>編輯會議原則

您可以編輯全域原則和您建立的任何自訂原則。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [會議 **]**  >  [會議原則 **]**。
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 從此處，進行您需要的變更。
4. 按一下 [儲存]。

> [!NOTE]
> 一次只能為使用者指派一個會議原則。

這段影片將示範編輯全組織預設會議原則的步驟。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53MoG?autoplay=false]

## <a name="assign-a-meeting-policy-to-users"></a>將會議原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> 如果已將原則指派給使用者，就無法刪除該原則。 您必須先為所有受影響的使用者指派不同的原則，之後才可以刪除原始原則。

## <a name="meeting-policy-settings"></a>會議原則設定

當您在 [ **會議** 原則] 頁面上選取現有原則，或選取 [ **新增** ] 以新增原則時，您可以為下列設定。

- [一般](meeting-policies-in-teams-general.md)
- [音訊與視訊](meeting-policies-audio-and-video.md)
- [錄製&稿](meetings-policies-recording-and-transcription.md)
- [內容共用](meeting-policies-content-sharing.md)
- [參與者與來賓](meeting-policies-participants-and-guests.md)

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](policy-assignment-overview.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議原則](meeting-policies-restricted-anonymous-access.md)
