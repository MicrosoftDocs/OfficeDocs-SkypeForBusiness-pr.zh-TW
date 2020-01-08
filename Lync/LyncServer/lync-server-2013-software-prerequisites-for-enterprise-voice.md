---
title: Lync Server 2013：Enterprise Voice 的軟體先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中 Enterprise Voice 的軟體先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

確認您要部署企業語音的基礎結構符合下列軟體先決條件：

  - Lync Server 2013 標準版或 Enterprise Edition 已安裝並在您的網路上運作。

  - 所有邊緣伺服器都是在您的周邊網路中部署和執行，包括執行存取邊緣服務的邊緣伺服器、A/V 邊緣服務、網頁會議 Edge 服務，以及反向 proxy。

  - 您可以使用 Microsoft Exchange Server 2007 Service Pack 3 （SP3）、Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013，以與 Lync Server 整合 Exchange 整合訊息，並提供豐富的通知及通話記錄資訊給Lync 端點。

  - 已為 Lync Server 建立並啟用一或多位使用者。

  - 已成功部署 Lync 用戶端和裝置。

  - 拓撲建立程式已安裝在您網路上的伺服器上。

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>後續步驟：驗證安全性與設定先決條件

驗證企業語音的軟體先決條件之後，您可以使用檔來繼續準備部署企業語音：

1.  驗證安全性、使用者設定和硬體 perquisites，如在[Lync Server 2013 的安全性和設定先決條件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述。

2.  安裝中繼伺服器，如在[Lync server 2013 中安裝用於進行轉送服務伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案中所述，但*僅限*您想要部署獨立的中繼伺服器或池，因為在 collocated 時，會將轉送伺服器安裝為前端池或標準版伺服器部署程式的一部分。

3.  設定幹線連線為使用者提供 PSTN 連線，如在[Lync Server 2013 中設定 trunks 中](lync-server-2013-configuring-trunks.md)所述。

</div>

</div>

<span> </span>

</div>

</div>

</div>

