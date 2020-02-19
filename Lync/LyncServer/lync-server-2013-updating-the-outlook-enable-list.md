---
title: Lync Server 2013： 更新 Outlook 啟用清單
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
ms.openlocfilehash: 1e1f71d1ef0ebcb6bc5f8aee8875c013a24a4de0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>更新 Lync Server 2013 中的 Outlook 啟用清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-07_

您可以確保，Online Meeting add-in for Microsoft Lync 2013 永遠保持啟用的使用者所建立的原則，包括其增益集管理清單中的 Outlook。 「增益集管理清單」原則包含在「群組原則管理主控台」的 Office 系統管理範本檔案中。 它會建立登錄機碼下 HKCU\\軟體\\原則\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList。 您可以 ucaddin.dll 值加入此機碼，並設定 ucaddin.dll 值，使它一律會啟用，以便讓使用者無法手動予以停用

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>若要將 ucaddin.dll 新增至 Outlook 增益集清單

  - AddinList 登錄機碼，位於 [HKCU\\軟體\\原則\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList，新增下列值：
    
      - 登錄類型 = 登錄\_Linkid
    
      - 名稱 = ucaddin.dll
    
      - 值 = 1 (指定增益集一律啟用，而且使用者無法管理)

</div>

</div>

<span> </span>

</div>

</div>

</div>

