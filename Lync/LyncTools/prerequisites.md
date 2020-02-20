---
title: 必要條件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5ffc74e80547df1dd451cd86d681e85befe334
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>必要條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-19_

有各種硬體、 軟體和系統組態需求，您必須先執行 Lync Server 2013 壓力及效能工具。

<div>

## <a name="client-hardware-requirements"></a>用戶端的硬體需求

若要執行 Lync Server 2013 部署，為每個 4500 使用者想要模擬，其負載上的 [Lync Server 2013 壓力及效能工具，您必須至少一個專用的電腦符合下列基本硬體需求：

  - 1gb 網路介面卡

  - 8 GB ram

  - 2 顆雙核心管理中心處理單位 (Cpu)

</div>

<div>

## <a name="client-software-requirements"></a>用戶端軟體需求

若要在 Lync Server 2013 部署上執行 [Lync Server 2013 壓力及效能工具，是支援的作業系統：

  - Windows Server 2012 作業系統

  - Windows Server 2008 作業系統 （64 位元版本）

在用戶端電腦必須符合下列軟體需求：

  - 您必須安裝[Microsoft.NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212)執行階段。

  - 在 Windows Server 2008/Windows Server 2012 上必須啟用桌面體驗功能。

  - 您必須擁有[Microsoft Visual c + + 2012年可轉散發套件](https://go.microsoft.com/fwlink/?linkid=143216)(x64) 安裝。

  - 完整設定的 Lync Server 2013 部署。

<div>


> [!IMPORTANT]  
> Microsoft Unified Communications Managed API (UCMA) 4.0 文件庫中隨附的安裝套件，讓 UCMA 則不需要，因此不應安裝用戶端電腦上。



</div>

</div>

<div>

## <a name="configuration-requirements"></a>設定需求

會執行 Lync Server 2013 壓力及效能工具的電腦必須被設定是根據下列需求：

1.  您必須網域或本機系統管理員群組的成員身分登入。

2.  無法執行 Lync Server 2013 壓力及效能工具 (LyncPerfTool.exe)，也執行 Lync Server 2013 元件的電腦上。

3.  您必須執行 Lync Server 2013 使用者建立工具 (UserProvisioningTool.exe)，Standard Edition server 或前端伺服器上的使用者帳戶所在的位置。 當多次時，會執行此工具時，Microsoft 整合通訊啟用每個使用者必須有唯一的電話號碼。

4.  分頁檔案大小應系統管理，或應該至少 1.5 倍 RAM 的數量系統上。

</div>

</div>

<span> </span>

</div>

</div>

</div>

