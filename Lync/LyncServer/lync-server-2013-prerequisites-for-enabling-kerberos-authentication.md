---
title: Lync Server 2013：啟用 Kerberos 驗證的必要條件
description: Lync Server 2013：啟用 Kerberos 驗證的必要條件。
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
ms.openlocfilehash: 65a45bad0eb249fdbc717fe05f080ce737c87c6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579919"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中啟用 Kerberos 驗證的先決條件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在啟用 Kerberos 驗證之前，請確定您已完成所有必要的設定和基礎結構準備工作：

  - 已擴充 Lync Server 2013 的 Active Directory 架構。

  - 已完成 Lync Server 2013 的 Active Directory 樹系準備。

  - 已完成 Lync Server 2013 的 Active Directory 網域準備工作。

  - 已成功安裝中央管理存放區及可供使用。

  - 已使用拓撲產生器建立及發行拓撲。

  - 已定義及部署需要 Web 服務的伺服器和角色，包括前端伺服器、Standard Edition 伺服器及 Director。

  - Internet Information Services (IIS) 會以建議的角色服務設定及部署，以支援 Lync Server 2013 中的 Web 服務。

符合先決條件後，您應該準備好建立一或多個帳戶，以供部署的 Kerberos 驗證使用之 Web 服務。 每個部署應至少建立一個 Kerberos 驗證帳戶。 不過，您可以為每個網站各建立一個帳戶，以在該網站提供本機 Kerberos 驗證。 每個網站只能指定一個 Kerberos 驗證帳戶。

</div>

<span> </span>

</div>

</div>

</div>

