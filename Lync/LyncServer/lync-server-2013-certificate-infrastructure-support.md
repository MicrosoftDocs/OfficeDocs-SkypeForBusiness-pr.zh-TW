---
title: Lync Server 2013 的憑證基礎結構支援
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
ms.openlocfilehash: dea4ea71564feca6c23c6d9e16b4ca336fa95e87
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 中的憑證基礎結構支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-07_

Lync Server 2013 需要公開金鑰基礎結構 (PKI) 來支援傳輸層安全性 (TLS) 和相互 TLS (MTLS) 連線。 根據預設，Lync Server 2013 被設定為使用 TLS 進行用戶端與伺服器連線。 MTLS 是用於伺服器之間的連線。

MTLS 憑證必須由 Lync Server 2013 的信任的憑證授權單位 (Ca) 所發出。 Lync Server 支援下列 Ca 所發出的憑證：

  - 內部 CA 發行的憑證：
    
      - Windows Server 2003 作業系統 CA
    
      - Windows Server 2008 作業系統 CA
    
      - Windows Server 2008 R2 作業系統 CA
    
      - Windows Server 2012 作業系統 CA
    
      - Windows Server 2012 R2 作業系統 CA

  - 公用 CA 發行的憑證

與其他應用程式和伺服器，例如 Exchange 2013 通訊需要受到其他應用程式和產品的憑證。 2013 版本，Lync Server 2013 與其他 Microsoft server 產品，包括 Exchange 2013 和 SharePoint Server 支援伺服器對伺服器驗證及授權的 Open Authorization (OAuth) 通訊協定。 如需詳細資訊，請參閱部署文件或作業文件中的[管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

從執行 Windows 7 作業系統、 Windows Server 2008 R2 作業系統和 Microsoft Office Communicator 2007 Phone Edition 的用戶端連線，Lync Server 2013 包含支援 （但不需要） 使用 sha-256 簽署的憑證密碼編譯雜湊函數。 為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。

如需有關憑證需求的詳細資訊，請參閱[憑證基礎結構需求 Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)中規劃文件。 如需使用萬用字元憑證的詳細資訊，請參閱支援文件中的[Lync Server 2013 中支援的萬用字元憑證](lync-server-2013-wildcard-certificate-support.md)。

</div>

<span> </span>

</div>

</div>

</div>

