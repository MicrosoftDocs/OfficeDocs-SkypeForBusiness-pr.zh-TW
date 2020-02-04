---
title: Lync Server 2013 憑證基礎結構支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc8cb5bdad02de4fcb407d7eb27960258a46dd3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 中的憑證基礎結構支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

Lync Server 2013 需要公開金鑰基礎結構（PKI）來支援傳輸層安全性（TLS）和相互 TLS （MTLS）連線。 根據預設，Lync Server 2013 已設定為使用 TLS 進行用戶端到伺服器連線。 MTLS 是用於伺服器之間的連線。

MTLS 憑證必須由 Lync Server 2013 的信任憑證授權單位（Ca）頒發。 Lync Server 支援從下列 Ca 頒發的憑證：

  - 從內部 CA 頒發的憑證：
    
      - Windows Server 2003 作業系統 CA
    
      - Windows Server 2008 作業系統 CA
    
      - Windows Server 2008 R2 作業系統 CA
    
      - Windows Server 2012 作業系統 CA
    
      - Windows Server 2012 R2 作業系統 CA

  - 從公用 CA 頒發的憑證

與其他應用程式和伺服器通訊（例如 Exchange 2013）需要其他應用程式和產品所支援的憑證。 針對2013版本，Lync Server 2013 及其他 Microsoft Server 產品（包括 Exchange 2013 和 SharePoint Server）支援開啟授權（OAuth）通訊協定，以進行伺服器對伺服器驗證和授權。 如需詳細資訊，請參閱在部署檔或作業檔中[管理 Lync server 2013 中的伺服器到伺服器驗證（OAuth）和合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

對於執行 Windows 7 作業系統、Windows Server 2008 R2 作業系統及 Microsoft Office Communicator 2007 Phone Edition 的用戶端的連線，Lync Server 2013 包含支援（但不需要）使用 SHA-256 簽署的憑證加密雜湊函數。 若要使用 SHA-256 支援外部存取，外部憑證是由使用 SHA-256 的公用 CA 所頒發。

如需證書需求的詳細資訊，請參閱規劃檔中的[Lync Server 2013 證書基礎結構需求](lync-server-2013-certificate-infrastructure-requirements.md)。 如需如何在證書中使用萬用字元的詳細資訊，請參閱支援檔中的[Lync Server 2013 中的萬用字元證書支援](lync-server-2013-wildcard-certificate-support.md)。

</div>

<span> </span>

</div>

</div>

</div>

