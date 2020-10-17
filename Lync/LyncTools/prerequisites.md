---
title: 必要條件
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f81299b2efdde3be262439528409d89abf369f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509130"
---
# <a name="prerequisites"></a>先決條件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

您需要執行 Lync Server 2013 壓力和效能工具，各有不同的硬體、軟體和系統設定需求。

<div>

## <a name="client-hardware-requirements"></a>用戶端硬體需求

若要在 Lync Server 2013 部署上執行 Lync Server 2013 壓力和效能工具，針對您想要模擬其負載的每一個4500使用者，您至少需要一部專用電腦，滿足下列基本硬體需求：

  - 1 gb 網路介面卡

  - 8 GB ram

  - 2顆雙核中央處理單位 (CPUs) 

</div>

<div>

## <a name="client-software-requirements"></a>用戶端軟體需求

若要在 Lync Server 2013 部署上執行 Lync Server 2013 壓力和效能工具，支援的作業系統包括：

  - Windows Server 2012 作業系統

  - Windows Server 2008 作業系統 (64-位版本) 

您的用戶端電腦必須符合下列軟體需求：

  - 您必須已安裝 [Microsoft .Net Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime。

  - 在 Windows Server 2008/Windows Server 2012 上，必須啟用桌面體驗功能。

  - 您必須安裝 [Microsoft Visual c + + 2012 可轉散發元件套件](https://go.microsoft.com/fwlink/?linkid=143216) (x64) 。

  - 完全設定的 Lync Server 2013 部署。

<div>


> [!IMPORTANT]  
> Microsoft 整合通訊 Managed API (UCMA) 4.0 文件庫會包含在安裝套件中，因此不需要 UCMA，也不應該安裝在用戶端電腦上。



</div>

</div>

<div>

## <a name="configuration-requirements"></a>設定需求

將執行 Lync Server 2013 壓力和效能工具的電腦必須依照下列需求進行設定：

1.  您必須以 Domain 或 Local Admins 群組成員的身分登入。

2.  Lync Server 2013 應力和效能工具 ( # A0) 無法在同時執行 Lync Server 2013 元件的電腦上執行。

3.  您必須在前端伺服器或使用者帳戶所在的 Standard Edition 伺服器上，執行 [Lync Server 2013] 使用者建立工具 ( # A0) 。 當該工具執行多次時，每個啟用 Microsoft 整合通訊的使用者都必須有唯一的電話號碼。

4.  頁面檔案大小應為系統管理，或至少應為系統上的 RAM 量的1.5 倍。

</div>

</div>

<span> </span>

</div>

</div>

</div>

