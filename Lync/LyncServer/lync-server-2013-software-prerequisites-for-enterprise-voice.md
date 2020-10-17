---
title: Lync Server 2013： Enterprise Voice 的軟體必要條件
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
ms.openlocfilehash: 5b504c498b2f07915f741e6c3172e911c7d40dae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519620"
---
# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的 Enterprise Voice 的軟體必要條件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

確認您想要部署 Enterprise Voice 的基礎結構符合下列軟體先決條件：

  - Lync Server 2013 Standard Edition 或 Enterprise Edition 已安裝且可在您的網路上運作。

  - 所有 Edge Server 都會在周邊網路中部署及運作，包括執行 Access Edge service 的 Edge Server、A/V Edge service、Web 會議 Edge service 及反向 proxy。

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3) ，則需要 Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013，才能整合 Exchange 整合通訊與 Lync Server，並將豐富通知及通話記錄資訊提供給 Lync 端點。

  - 有一或多個使用者已建立並啟用 Lync Server。

  - 已成功部署 Lync 用戶端和裝置。

  - 拓撲產生器是安裝在網路上的伺服器上。

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>後續步驟：確認安全性和設定先決條件

確認 Enterprise Voice 的軟體先決條件後，您可以參考文件說明，繼續準備部署 Enterprise Voice：

1.  依照 [Lync Server 2013 的安全性和設定先決條件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述，驗證安全性、使用者設定和硬體 perquisites。

2.  如在 [Lync server 2013 中安裝轉送伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案所述，安裝轉送伺服器，但 *只有* 在您想要部署獨立轉送伺服器或集區時，因為在組合時已將轉送伺服器安裝為前端集區或 Standard Edition Server 部署程式的一部分。

3.  設定主幹連線以為使用者提供 PSTN 連線能力，如在 [Lync Server 2013 中設定主幹中](lync-server-2013-configuring-trunks.md)所述。

</div>

</div>

<span> </span>

</div>

</div>

</div>

