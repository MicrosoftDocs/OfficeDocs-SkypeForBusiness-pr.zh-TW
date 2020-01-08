---
title: 先決條件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74603ed20fe144ca89d3ac13bc00fef0e7d6ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

您必須執行 Lync Server 2013 應力和效能工具，才能執行各種硬體、軟體及系統設定需求。

<div>

## <a name="client-hardware-requirements"></a>用戶端硬體需求

若要在 Lync Server 2013 部署上執行 Lync Server 2013 應力和效能工具，請針對您想要模擬其負載的每個4500使用者，至少需要一個符合下列最低硬體需求的專用電腦：

  - 1個十億位元網路介面卡

  - 8 GB 的 ram

  - 2個雙核中央處理單元（Cpu）

</div>

<div>

## <a name="client-software-requirements"></a>用戶端軟體需求

若要在 Lync Server 2013 部署上執行 Lync Server 2013 壓力與效能工具，支援的作業系統如下：

  - Windows Server 2012 作業系統

  - Windows Server 2008 作業系統（64位版本）

您的用戶端電腦必須符合下列軟體需求：

  - 您必須已安裝[Microsoft .Net Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212)執行時間。

  - 在 Windows Server 2008/Windows Server 2012 上，必須啟用 [桌面體驗] 功能。

  - 您必須已安裝[Microsoft Visual c + + 2012 可再發行套件](http://go.microsoft.com/fwlink/?linkid=143216)（x64）。

  - 完全設定的 Lync Server 2013 部署。

<div>


> [!IMPORTANT]  
> Microsoft 整合通訊管理 API （UCMA）4.0 文件庫包含在安裝套件中，因此不需要 UCMA，也不應該在用戶端電腦上安裝。



</div>

</div>

<div>

## <a name="configuration-requirements"></a>配置需求

將執行 Lync Server 2013 壓力與效能工具的電腦，必須依照下列需求進行設定：

1.  您必須以網域或本機系統管理員群組的成員的身分登入。

2.  Lync Server 2013 應力和效能工具（LyncPerfTool）無法在同時執行 Lync Server 2013 元件的電腦上執行。

3.  您必須在前端伺服器或使用者帳戶將駐留的標準版伺服器上執行 Lync Server 2013 使用者建立工具（UserProvisioningTool）。 當工具多次執行時，每個啟用 Microsoft 整合通訊的使用者都必須有唯一的電話號碼。

4.  頁面檔案大小應由系統管理，或至少1.5 倍于系統的 RAM 數量。

</div>

</div>

<span> </span>

</div>

</div>

</div>

