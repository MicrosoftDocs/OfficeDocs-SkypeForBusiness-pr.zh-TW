---
title: Lync Server 2013：規劃 Edge Server 憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faad6dba610df8033b75b0c87c52fbb065dc5dcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>在 Lync Server 2013 中規劃 Edge Server 憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-05_

在 Lync Server 2013 中簡化了邊緣的證書建立。

**Edge Server 的憑證流程圖**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

建立單一公用憑證，請確定您已為憑證定義可匯出的私密金鑰，然後使用憑證嚮導將它指派給下列 Edge 伺服器外部介面：

<div>


> [!IMPORTANT]  
> Lync Server 不支援萬用字元憑證，除非使用反向 proxy 來摘要簡單的 Url。 您必須針對您的部署提供的每個 SIP 功能變數名稱、網頁會議 Edge 服務、A/V Edge 服務和 XMPP 網域，定義不同的主體替換名稱（San）。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 中引入，在目前憑證的到期時間前暫存音訊/視頻驗證憑證需要額外的規劃。 在外部邊緣介面的情況下，不需要使用一個以上用途的憑證，您必須有兩個憑證，一個指派給 [存取邊緣] 服務和 [Web 會議 Edge 服務]，另一個是 A/V 邊緣服務的憑證。 如需其他詳細資料，請參閱<A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">使用 CsCertificate 中的 [在 Lync Server 2013 中暫存 AV 和 OAuth 憑證</A>]



</div>

<div>


> [!IMPORTANT]  
> 在邊緣伺服器池的事件中，您會將擁有私密金鑰的憑證匯出至每個 Edge 伺服器，並將憑證指派給每個 Edge 伺服器服務。 對內部邊緣伺服器憑證執行相同的動作，以私密金鑰匯出憑證，並指派給每個內部邊緣介面。



</div>

  - 確定您已為憑證指派可匯出的私人金鑰

  - Access Edge 服務（在證書嚮導中稱為**SIP 存取邊緣**）

  - 網路會議 Edge 服務（在證書嚮導中稱為「**網路會議 Edge 外部**」）

  - A/V 驗證服務（在證書嚮導中稱為**a/v 邊緣**）

使用可匯出的私密金鑰建立單一的內部憑證，將它複製並指派給每一個 Edge 伺服器內部介面：

  - Edge 伺服器（在證書嚮導中稱為**邊緣內部**）

<div>


> [!IMPORTANT]  
> 您可以針對每個 Edge 伺服器服務使用不同且不同的憑證。 若要使用 A/V 邊緣服務憑證的新的 [滾動憑證] 功能，選擇 [個別憑證] 的最佳原因是。 在這項功能的情況下，建議您將 A/V Edge 服務憑證與 [存取邊緣服務] 和 [Web 會議 Edge 服務] 相分離。 如果您選擇要求、針對每個服務取得並指派個別的憑證，您必須要求將私密金鑰匯出為 A/v 邊緣服務（同樣地，這實際上是 A/V 驗證服務），並將相同的憑證指派給每個 Edge 伺服器上的 A/V 邊緣外部介面。



</div>

<div>

## <a name="see-also"></a>請參閱


[使用 CsCertificate 在 Lync Server 2013 中暫存 AV 和 OAuth 憑證](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[在 Lync Server 2013 中會影響 Edge Server 規劃的變更](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

