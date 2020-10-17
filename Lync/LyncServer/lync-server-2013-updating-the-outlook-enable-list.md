---
title: Lync Server 2013：更新 Outlook 啟用清單
description: Lync Server 2013：更新 Outlook 啟用清單。
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
ms.openlocfilehash: 96edc327fa1b63d5da95eb6ea36a2296659910d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546229"
---
# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>在 Lync Server 2013 中更新 Outlook 啟用清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-07_

您可以在 Outlook 的增益集管理清單中建立一個原則，以確保 Microsoft Lync 2013 的線上會議增益集永遠保持啟用狀態，以供使用者使用。 「增益集管理清單」原則包含在「群組原則管理主控台」的 Office 系統管理範本檔案中。 它會在 [HKCU 軟體原則] 下的 [ \\ \\ \\ Microsoft \\ Office \\ 15.0 \\ Outlook15 \\ 恢復 \\ AddinList] 底下建立登錄機碼。 您可以將 ucaddin.dll 的值加入至此機碼，並設定 ucaddin.dll 值，使其永遠啟用，且使用者無法手動加以停用。

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>將 ucaddin.dll 新增至 Outlook 增益集清單

  - 在 [AddinList] 登錄機碼（位於 [HKCU \\ 軟體 \\ 原則] \\ Microsoft \\ Office \\ 15.0 \\ Outlook15 \\ 恢復 \\ AddinList）下，新增下列值：
    
      - 登錄類型 = REG \_ SZ
    
      - 名稱 = ucaddin.dll
    
      - 值 = 1 (指定增益集一律啟用，而且使用者無法管理)

</div>

</div>

<span> </span>

</div>

</div>

</div>

