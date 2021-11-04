---
title: 用戶端版本規則
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: 用戶端版本原則是由一組用戶端版本規則所組成。當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。
ms.openlocfilehash: e24921156470b1a91dc9f7421913c1fa6da1ef35
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769531"
---
# <a name="client-version-rule"></a>用戶端版本規則

用戶端版本原則是由一組用戶端版本規則所組成。當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「新增用戶端版本設定」或「編輯用戶端版本設定」頁面上執行下列工作：

- 新增規則至用戶端版本原則。

- 修改組成現有用戶端版本原則的規則

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。


- **使用者代理程式** 您可以從清單中選取用戶端類型。 下表定義使用者代理程式碼。 此清單包含舊版用戶端類型，其中一些已不再支援。

|**用戶端名稱**|**使用者代理程式**|
|:-----|:-----|
|lync 2013、lync 2010 Office Communicator  <br/> |OC  <br/> |
|Lync web App （Communicator Web 存取）  <br/> |NM-CWA-13-NO-VERSION  <br/> |
|Lync 電話 Edition，Office Communicator 電話  <br/> |OCPhone  <br/> |
|Communicator Phone Edition 平台  <br/> |CPE  <br/> |
|Unified Communications 平台  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting 增益集  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows信使  <br/> |WM  <br/> |
|即時通訊用戶端  <br/> |RTC  <br/> |
|iPad 的 Lync 2010  <br/> |iPadLync  <br/> |
|iPhone 的 Lync 2010  <br/> |iPhoneLync  <br/> |
|Windows Phone 的 Lync 2010  <br/> |WPLync  <br/> |
|Lync 2010 for Nokia  <br/> |NokiaLync  <br/> |
|適用于 Android 的 Lync 2010  <br/> |AndroidLync  <br/> |
|行動性服務  <br/> |McxService  <br/> |

- **版本號碼** 您可以指定下欄欄位的版本號碼，或使用萬用字元表示用戶端版本號碼。

  - **主要版本** 指定對應至用戶端主要版本的號碼。

  - **次要版本** 指定對應至用戶端次要版本的號碼。

  - **組建** 指定對應至用戶端主要和次要版本的組建編號。

  - **更新** 指定對應至用戶端更新版本的號碼。

- **比較運算** 您可以指定您在上述步驟中指定之用戶端版本的對應作業。 可供使用的作業如下：

  - **相同**

  - **不相同**

  - **新於**

  - **新於或相同**

  - **舊於**

  - **舊於或相同**

- **動作** 您可以指定在上述步驟中符合準則時所要執行的動作。 可供使用的動作如下：

  - **允許** 允許用戶端登入。

  - **允許和升級** 允許用戶端登入或接收 Windows Server Update Service 或 Microsoft Update 的更新。 只有在選取 [使用者代理 **OC** ] 時，才可使用此動作。

    > [!NOTE]
    > 選取此動作會在使用者下一次登入商務用 Skype 時顯示通知。 通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。 若要避免混淆，您應該僅在更新可用時選擇此動作。

  - **允許搭配 URL** 允許用戶端登入並顯示從何處下載其他用戶端版本的訊息。 您要在 [URL] 欄位中指定 URL。

  - **封鎖** 禁止用戶端登入。

  - **封鎖和升級** 防止用戶端登入，並且允許用戶端從 Windows Server Update Service 或 Microsoft Update 接收更新。 只有在選取 [使用者代理 **OC** ] 時，才可使用此動作。

  - **以 URL 封鎖** 禁止用戶端登入並且顯示哪裡可以下載其他用戶端版本的訊息。您要在 [URL] 欄位中指定 URL。

如需用戶端與用戶端版本之間的互用性相關詳細資訊，請參閱規劃檔中的 [用戶端互通性](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 。 如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的＜[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)＞。