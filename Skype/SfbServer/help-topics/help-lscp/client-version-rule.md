---
title: 用戶端版本規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: 用戶端版本原則是由一組用戶端版本規則所組成。當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。
ms.openlocfilehash: 6fa3ca3f59756c8a6fedb9fd8f1f457ca3f2df40
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188053"
---
# <a name="client-version-rule"></a>用戶端版本規則

用戶端版本原則是由一組用戶端版本規則所組成。當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「新增用戶端版本設定」**** 或「編輯用戶端版本設定」**** 頁面上執行下列工作：

- 新增規則至用戶端版本原則。

- 修改組成現有用戶端版本原則的規則

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- **使用者代理程式**您可以從清單中選取用戶端類型。 下表定義使用者代理程式碼。

|**用戶端名稱**|**使用者代理程式**|
|:-----|:-----|
|Lync 2013、Lync 2010、Office Communicator  <br/> |OC  <br/> |
|Lync Web App、Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition、Office Communicator Phone  <br/> |OCPhone  <br/> |
|Communicator Phone Edition 平台  <br/> |CPE  <br/> |
|整合通訊平台  <br/> |UCCP  <br/> |
|Lync 2010 出席者  <br/> |AOC  <br/> |
|Live Meeting 增益集  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|即時通訊用戶端  <br/> |RTC  <br/> |
|IPad 版 Lync 2010  <br/> |iPadLync  <br/> |
|IPhone 版 Lync 2010  <br/> |iPhoneLync  <br/> |
|Windows Phone 版 Lync 2010  <br/> |WPLync  <br/> |
|適用于 Nokia 的 Lync 2010  <br/> |NokiaLync  <br/> |
|Android 版 Lync 2010  <br/> |AndroidLync  <br/> |
|行動性服務  <br/> |McxService  <br/> |

- **版本號碼**您可以指定下欄欄位的版本號碼, 或使用萬用字元來表示用戶端的版本號碼。

  - **主要版本**指定與用戶端主要版本相對應的數位。

  - **次要版本**指定與用戶端次要發行版本相對應的數位。

  - **組建**指定與用戶端主要和次要版本相對應的組建編號。

  - **更新**指定與用戶端更新版本相對應的數位。

- **比較運算**您可以針對您在上述步驟中所指定的用戶端版本, 指定相符的操作。 下列作業可供使用:

  - **相同**

  - **不相同**

  - **新於**

  - **新於或相同**

  - **舊於**

  - **舊於或相同**

- **動作**您可以指定在滿足上述步驟中的準則時要執行的動作。 下列動作可供使用:

  - **允許**允許用戶端登入。

  - **允許和升級**允許用戶端登入, 並從 Windows Server Update Services 或 Microsoft Update 接收更新。 只有在選取 [使用者代理**OC** ] 時, 才能使用此動作。

    > [!NOTE]
    > 選取此動作會在使用者下次登入商務用 Skype 時, 顯示通知。 通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。 為避免混淆，您應該僅在有可用更新時選擇此動作。

  - **允許 URL**允許用戶端登入, 並顯示有關下載其他用戶端版本之位置的訊息。 您要在 [URL]**** 欄位中指定 URL。

  - **封鎖**防止用戶端登入。

  - **封鎖和升級**防止用戶端登入, 並允許用戶端從 Windows Server Update Services 或 Microsoft Update 接收更新。 只有在選取 [使用者代理**OC** ] 時, 才能使用此動作。

  - **以 URL 封鎖** 禁止用戶端登入並且顯示哪裡可以下載其他用戶端版本的訊息。您要在 [URL]**** 欄位中指定 URL。

如需用戶端和用戶端版本間互通性的詳細資訊，請參閱規劃文件中的〈[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)〉。如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的〈[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)〉。

