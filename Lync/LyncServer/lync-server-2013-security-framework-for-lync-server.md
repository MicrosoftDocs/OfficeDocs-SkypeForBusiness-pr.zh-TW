---
title: Lync Server 2013： Lync Server 的安全性框架
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f84b7eaf3476624479d1ecb7c7bb564a4eae8ad9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510440"
---
# <a name="security-framework-for-lync-server-2013"></a>Lync Server 2013 的安全性框架

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-08_

本節提供組成 Microsoft Lync Server 2013 安全性框架之基礎元素的概述。 瞭解這些元素的運作方式，對於在保護特定 Lync Server 2013 部署的相關決策方面是必要的。

這些元素如下：

  - Active Directory 網域服務 (AD DS) 提供使用者帳戶和網路資源的單一信任後端存放庫。

  - Role-Based 存取控制 (RBAC) 可讓您委派管理工作，同時維持高安全性標準。

  - 公開金鑰基礎結構 (PKI) 會使用受信任的憑證授權單位單位 (CAs) 所發行的憑證，以驗證服務器並確保資料完整性。

  - 傳輸層安全性 (TLS) 、HTTPS over SSL (HTTPS) ，以及相互 TLS (MTLS) 啟用端點驗證和 IM 加密。 使用安全 Real-Time 傳輸通訊協定 (SRTP) ，對點對點音訊、影片和應用程式共用資料流程進行加密。

  - 適用于使用者驗證的業界標準通訊協定。

  - Windows PowerShell 提供預設啟用的安全性功能，讓使用者無法輕易或無意中執行腳本。

這些基本的安全性元素共同運作，以定義信任的使用者、伺服器、連線和作業，以協助確保 Lync Server 2013 的安全基礎。

<div>

## <a name="in-this-section"></a>本章節內容

本節中的主題說明這些基本元素的運作方式，以加強 Lync Server 基礎結構的安全性。

  - [Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013 的以角色為基礎的存取控制 (RBAC) ](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013 的公用機碼基礎結構](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 的 TLS 和 MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013 的加密](lync-server-2013-encryption.md)

  - [Lync Server 2013 的使用者和用戶端驗證](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell 和 Lync Server 2013 管理工具](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

