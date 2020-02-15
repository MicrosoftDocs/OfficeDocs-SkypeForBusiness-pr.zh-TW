---
title: 'Lync Server 2013: Lync server 的安全性架構'
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
ms.openlocfilehash: 9910b4c481ea474425cae51d7fac88a217d52e1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Lync Server 2013 的安全性架構

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-08_

本章節提供基本元素，讓表單 Microsoft Lync Server 2013 的安全性架構的概觀。 了解這些項目共同運作的方式是不可或缺的相關保護您特定的 Lync Server 2013 部署明智決策。

這些元素如下所示：

  - Active Directory 網域服務 (AD DS) 提供單一受信任的後端儲存機制的使用者帳戶及網路資源。

  - 角色型存取控制 (RBAC) 可讓您管理工作委派維持高標準的安全性。

  - 公開金鑰基礎結構 (PKI) 使用受信任的憑證授權單位 (Ca) 所發出的憑證來驗證伺服器，並確保資料完整性。

  - 傳輸層安全性 (TLS) HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 啟用端點驗證及 IM 加密。 使用安全即時傳輸通訊協定 (SRTP) 會加密點對點音訊、 視訊及應用程式共用資料流。

  - 請儘可能進行使用者驗證通訊協定業界標準。

  - Windows PowerShell 提供的安全性功能，讓使用者無法輕易地或不知情的情況下執行指令碼，依預設而啟用。

這些基本安全性要素會共同運作來定義信任的使用者、 伺服器、 連線以及作業，以協助確保 Lync Server 2013 的安全基礎。

<div>

## <a name="in-this-section"></a>本章節內容

本節中的主題會說明每個這些基礎元素增強安全性，Lync Server 基礎結構的運作方式。

  - [Lync Server 2013 的 active Directory 網域服務](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013 的角色型存取控制 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013 的公開金鑰基礎結構](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 的 TLS 和 MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013 的加密](lync-server-2013-encryption.md)

  - [Lync Server 2013 的使用者與用戶端驗證](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell 和 Lync Server 2013 管理工具](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

