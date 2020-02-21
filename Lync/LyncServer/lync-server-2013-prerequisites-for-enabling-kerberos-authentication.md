---
title: 啟用 Kerberos 驗證的 Lync Server 2013： 必要條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dd399ef7a0ed2dd6609fe0455d9593e1e567b3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>啟用 Lync Server 2013 中的 Kerberos 驗證的必要條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

之前啟用 Kerberos 驗證，請確定您完成所有必要的組態和基礎結構的準備工作：

  - 針對 Lync Server 2013 會延伸 active Directory 架構。

  - Lync Server 2013 已完成 active Directory 樹系準備。

  - Lync Server 2013 已完成 active Directory 網域準備工作。

  - 中央管理存放區已成功安裝且可用。

  - 建立並發佈使用拓撲產生器拓樸。

  - 伺服器需要 Web 服務的角色已定義並部署，包括前端伺服器、 Standard Edition server 和 Director。

  - 網際網路資訊服務 (IIS) 是設定及部署以支援 Lync Server 2013 中的 Web 服務的建議的角色服務。

在符合必要條件之後，您應該可以準備建立要用於部署的 Kerberos 驗證的 Web 服務的一或多個帳戶。 每個部署應至少建立一個 Kerberos 驗證帳戶。 不過，您可以為每個網站各建立一個帳戶，以在該網站提供本機 Kerberos 驗證。 每個網站只能指定一個 Kerberos 驗證帳戶。

</div>

<span> </span>

</div>

</div>

</div>

