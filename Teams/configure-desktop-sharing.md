---
title: 在 Microsoft 團隊中設定桌面共用
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 設定會議原則，讓使用者在團隊聊天或會議中共用其桌面
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99c6e2a5adb9d0f9a4b4e3f6f17b7484bda96a74
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "37516883"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>在 Microsoft 團隊中設定桌面共用
============================================

桌面共用可讓使用者在會議或聊天期間呈現畫面或應用程式。 系統管理員可以在 Microsoft 團隊中設定螢幕共用，讓使用者共用整個螢幕、應用程式或檔案。 您可以讓使用者提供或要求控制、允許 PowerPoint 共用、新增白板，以及允許共用筆記。 您也可以設定匿名或外部使用者是否可以要求共用畫面的控制權。

若要設定螢幕共用，您需要建立新的會議原則，然後將它指派給您想要管理的使用者。

**在 Microsoft 團隊系統管理中心**

1. 選取 [**會議** > **會議原則**]。

    ![顯示已選取會議原則的螢幕擷取畫面](media/configure-desktop-sharing-image1.png)

2. 在 [**會議原則**] 頁面上，選取 [**新增原則**]。

    ![顯示會議原則訊息的螢幕擷取畫面](media/configure-desktop-sharing-image2.png)

3. 為您的原則命名唯一的標題，然後輸入簡短的描述。

4. 在 [**內容共用**] 底下，從下拉式清單中選擇**螢幕共用模式**：

   - **整個畫面**-讓使用者共用其整個桌面。
   - **單一應用程式**-讓使用者將螢幕共用限制在單一作用中的應用程式。
   - [**已停用**]-關閉螢幕共用。

    ![顯示共用模式選項的螢幕擷取畫面](media/configure-desktop-sharing-image3.png)

5. 開啟或關閉下列設定：

    - [**允許參與者授與要求控制**]：讓小組成員可以授與要求控制簡報者的桌面或應用程式。
    - [**允許外部參與者授與要求控制**]：讓來賓與外部（同盟）使用者提供或要求簡報者的桌面或應用程式的控制權。
    - [**允許 powerpoint 共用**]：可讓使用者建立可讓 PowerPoint 簡報上傳及共用的會議。
    - [**允許使用白板**]-讓使用者共用白板。
    - [**允許共用筆記**]：讓使用者取得共用筆記。

6. 按一下 [**儲存**]。

## <a name="use-powershell-to-configure-shared-desktop"></a>使用 PowerShell 來設定共用桌面

您也可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) Cmdlet 來控制桌面共用。 設定下列參數：

- 說明
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[深入瞭解如何使用 csTeamsMeetingPolicy Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。

