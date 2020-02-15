---
title: 'Lync Server 2013: Enterprise Voice 的軟體先決條件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc6c5e5f3f9fc92f56ee1f044419f67f5ded32ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的 Enterprise Voice 的軟體先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

確認您想要部署 Enterprise Voice 的基礎結構符合下列軟體先決條件：

  - Lync Server 2013 Standard Edition 或 Enterprise Edition 已安裝且正在運作您網路上。

  - 所有 Edge Server 都都已部署、 作業在周邊網路，包括 Edge 伺服器執行 Access Edge service 為 A / V Edge service、 Web Conferencing Edge service 和反向 proxy。

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3)、 Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013 才整合 Exchange 整合通訊與 Lync Server，以及用於提供豐富的通知及通話記錄資訊Lync 端點。

  - 已建立並啟用 Lync Server 的一或多個使用者。

  - Lync 用戶端和裝置已成功部署。

  - 在您網路上的伺服器上安裝拓撲產生器]。

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>後續步驟：確認安全性和設定先決條件

確認 Enterprise Voice 的軟體先決條件後，您可以參考文件說明，繼續準備部署 Enterprise Voice：

1.  確認安全性、 使用者設定和硬體 environmental [Lync Server 2013 中的 Enterprise voice 的安全性和組態必要條件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述。

2.  安裝中繼伺服器中所述[安裝中繼伺服器在 Lync Server 2013 中的檔案](lync-server-2013-install-the-files-for-mediation-server.md)，但*僅限*如果您想要部署獨立中繼伺服器或集區，因為中繼伺服器安裝為前端集區或 Standard Edition server 部署程序時組合的一部分。

3.  設定主幹連線以提供 PSTN 連線的使用者，[在 Lync Server 2013 中的 Configuring trunks](lync-server-2013-configuring-trunks.md)中所述。

</div>

</div>

<span> </span>

</div>

</div>

</div>

