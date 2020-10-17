---
title: Lync Server 2013：確認拓撲設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e8dae20a945194fb4fda2bcc84eab232d9b34e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518590"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a>驗證 Lync Server 2013 中的拓撲設計

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-01-02_

拓撲產生器會自動驗證拓撲。 任何拓撲錯誤都會識別為驗證錯誤，由伺服器角色旁邊的驗證錯誤圖示所指示。 此外，驗證此拓撲是否正確表示您的部署拓撲也很重要。

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>若要在發行之前驗證拓撲

1.  檢查所有簡單 URL 皆已設定正確。

2.  確認以 SQL Server 為基礎的伺服器在線上，且可供安裝拓撲產生器的電腦使用（包括任何必要的防火牆規則）。

3.  確認檔案共用可用且具有適當的許可權定義。

4.  確認拓撲中已定義符合部署需求的正確伺服器角色。

5.  確認伺服器存在於 Active Directory 網域服務中。 如果您已將伺服器加入至網域，則會自動發生這種情形。

當您已驗證拓撲且沒有驗證錯誤時，您應可準備發行拓撲。 如果有驗證錯誤，您必須先更正錯誤，才可以發行拓撲。 如需有關發佈拓撲的詳細資訊，請參閱 [在 Lync Server 2013 中發行拓撲](lync-server-2013-publish-the-topology.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

