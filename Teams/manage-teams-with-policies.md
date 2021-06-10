---
title: 使用Teams管理
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 瞭解Teams政策。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77afc1cbb71fff9cb54decbbf6e5cfd10d6c4e59
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574182"
---
# <a name="manage-teams-with-policies"></a>使用Teams管理

策略是管理系統管理的重要Teams。 使用本文流覽如何使用策略來為貴組織帶來好處。

## <a name="what-you-use-policies-for"></a>您用於策略的

策略是用來在貴組織中完成跨不同領域的許多工作，例如訊息、會議和應用程式。 您可以執行一些操作，包括允許使用者在團隊頻道中排程會議、讓使用者編輯已送出的郵件，以及控制使用者是否可以將應用程式釘Teams應用程式欄。

## <a name="how-to-assign-policies"></a>如何指派策略

您可以根據貴組織嘗試完成的工作，以多種方式指派策略。 您可以在系統管理中心進行Teams作業。

![群群組原則作業的螢幕擷取畫面。](media/group-policy-assignment.png)

深入瞭解如何在這裡指派 [策略](policy-assignment-overview.md)。

## <a name="how-to-manage-policies"></a>如何管理原則

使用系統管理中心Microsoft Teams使用[PowerShell 管理原則](./teams-powershell-managing-teams.md#manage-policies-via-powershell)。

例如，應用程式設定策略可以允許使用者上傳自訂應用程式、代表使用者安裝應用程式，以及將應用程式釘Teams欄。 這些策略在系統管理中心Teams中。

![應用程式設定策略的螢幕擷取畫面。](media/app-setup-policy.png)

此外，會議策略可用來控制會議中的音訊和視Teams設定，例如文字翻譯、雲端錄製和 IP 音訊/視像。

![會議策略的螢幕擷取畫面。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>適用於教育的 Teams

您也可以使用教育Teams精靈[](easy-policy-setup-edu.md)，輕鬆設定和管理學習環境的政策。

![教育Teams精靈的螢幕擷取畫面。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>政策類型

下列政策可以使用 Microsoft Teams。

策略類型 | 描述
------------|------------
[策略套件](manage-policy-packages.md) | 其中一個Microsoft Teams套件是一組預先定義的策略和設定，您可以指派給組織中具有類似角色的使用者。
[會議原則](meeting-policies-in-teams.md) | 會議策略是用來控制貴組織中使用者排程會議之會議參與者可用的功能。 會議政策包含下列主題。<br> - 音訊和視音訊政策<br> - 內容和螢幕畫面共用政策<br> - 參與者、來賓和存取政策<br> - 一般政策
[語音和通話政策](voice-and-calling-policies.md)| 語音和通話政策會透過團隊管理這些設定，例如緊急通話、呼叫路由和本機號碼。
[應用程式政策](app-policies.md)| 應用程式策略用於控制應用程式Microsoft Teams。 系統管理員可以允許或封鎖使用者可以安裝的應用程式、將應用程式釘Teams使用者的應用程式欄，以及代表使用者安裝應用程式。
[訊息原則](messaging-policies-in-teams.md)| 訊息策略可控制聊天和頻道功能的可用性。

## <a name="related-topics"></a>相關主題

* [在 Teams 中指派Teams - 開始使用](policy-assignment-overview.md)
* [管理意見Microsoft Teams](manage-feedback-policies-in-teams.md)
* [管理團隊Microsoft Teams](teams-policies.md)
* [在 Microsoft Teams 中設定即時活動](teams-live-events/set-up-for-teams-live-events.md)
* [Teams教育政策與政策套件](policy-packages-edu.md)