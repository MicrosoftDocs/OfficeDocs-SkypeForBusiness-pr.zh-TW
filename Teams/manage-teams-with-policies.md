---
title: 使用原則管理Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 深入瞭解Teams原則。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 932fed6b2a735aabee0511b6f1c6b863e01e403c
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646482"
---
# <a name="manage-teams-with-policies"></a>使用原則管理Teams

原則是管理Teams的重要部分。 使用本文流覽如何使用原則來使貴組織受益。

## <a name="what-you-use-policies-for"></a>您使用原則的內容

原則可用來完成貴組織中許多不同領域的工作，例如傳訊、會議和應用程式。 您可以執行的一些動作包括允許使用者在團隊頻道中排程會議、讓使用者編輯已傳送的訊息，以及控制使用者是否可以將應用程式釘選到Teams應用程式行。

## <a name="how-to-assign-policies"></a>如何指派原則

您可以根據貴組織嘗試完成的工作，以數種不同的方式指派原則。 您可以在系統管理中心Teams作業並檢視作業。

![群組原則指派的螢幕擷取畫面。](media/group-policy-assignment.png)

在這裡深入瞭解指[派原則。](policy-assignment-overview.md)

## <a name="how-to-manage-policies"></a>如何管理原則

原則是透過Microsoft Teams系統管理中心或[使用 PowerShell 來管理](./teams-powershell-managing-teams.md#manage-policies-via-powershell)。

例如，應用程式設定原則可以讓使用者上傳自訂應用程式、代表您的使用者安裝應用程式，以及將應用程式釘選到Teams應用程式行。 這些原則是在系統管理中心Teams設定的。

![應用程式設定原則的螢幕擷取畫面。](media/app-setup-policy.png)

此外，會議原則可用來控制Teams會議中的音訊和視訊設定，例如轉譯、雲端錄製和 IP 音訊/視訊。

![會議原則的螢幕擷取畫面。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>適用於教育的 Teams

您也可以使用[Teams 教育版原則精](easy-policy-setup-edu.md)靈，輕鬆設定和管理學習環境的原則。

![Teams 教育版原則精靈的螢幕擷取畫面。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>原則類型

您可以使用Microsoft Teams來管理下列原則。

原則類型 | 描述
------------|------------
[原則套件](manage-policy-packages.md) | Microsoft Teams中的原則套件是一組預先定義的原則和設定，您可以指派給組織中具有類似角色的使用者。
[會議原則](meeting-policies-overview.md) | 會議原則可用來控制組織中使用者排程之會議的會議參與者可用的功能。 會議原則包括下列主題。<br> - 音訊和視訊原則<br> - 內容和螢幕共用原則<br> - 參與者、來賓和存取原則<br> - 一般原則
[語音和通話原則](voice-and-calling-policies.md)| 語音和通話原則會透過小組管理這些設定，例如緊急通話、通話路由和來電者識別碼。
[應用程式原則](app-policies.md)| 應用程式原則是用來控制Microsoft Teams中的應用程式。 系統管理員可以允許或封鎖哪些應用程式使用者可以安裝、將應用程式釘選到使用者的Teams應用程式行，以及代表您的使用者安裝應用程式。
[訊息原則](messaging-policies-in-teams.md)| 訊息原則可控制聊天和頻道功能的可用性。

## <a name="related-topics"></a>相關主題

* [在 Teams 中指派原則 - 快速入門](policy-assignment-overview.md)
* [在 Microsoft Teams 中管理意見反應原則](manage-feedback-policies-in-teams.md)
* [在 Microsoft Teams 中管理團隊原則](teams-policies.md)
* [在 Microsoft Teams 中設定即時活動](teams-live-events/set-up-for-teams-live-events.md)
* [Teams 教育版原則和原則套件](policy-packages-edu.md)