---
title: Lync Server 2013：更新 Outlook 啟用清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44de6e3b7756935829b008c585474e08f6f9969
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>更新 Lync Server 2013 中的 Outlook 啟用清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-07_

您可以在 Outlook 的增益集管理清單中建立一個策略，以確保 Microsoft Lync 2013 的 [線上會議] 增益集能一直保持為使用者啟用。 增益集管理清單原則包含在群群組原則管理主控台的 Office 系統管理範本檔案中。 它會在\\[HKCU 軟體\\策略\\] 下，\\建立\\Microsoft\\Office\\15.0\\Outlook15 復原 AddinList 的登錄機碼。 您可以將 ucaddin 的值加到此索引鍵，並設定 ucaddin 的值，讓使用者不能手動將它停用。

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>若要將 ucaddin 新增至 Outlook 增益集清單

  - 在 AddinList 登錄機碼（位於 [HKCU\\軟體\\原則\\]\\底下\\的\\[\\Microsoft\\Office 15.0 Outlook15 復原 AddinList] 中，新增下列值：
    
      - 註冊表類型 = REG\_SZ
    
      - Name = ucaddin
    
      - 值 = 1 （指定該增益集永遠啟用，且無法由最終使用者管理）

</div>

</div>

<span> </span>

</div>

</div>

</div>

