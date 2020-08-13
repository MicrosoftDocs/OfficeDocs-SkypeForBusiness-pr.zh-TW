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
ms.openlocfilehash: 47ac330914a0d748c366d2a6e40ac0ad9f03543d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>在 Lync Server 2013 中規劃 Edge Server 憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-05_

在 Lync Server 2013 中簡化了 Edge 的憑證建立。

**Edge Server 的憑證流程圖表**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

建立單一公用憑證，請確定您具有為憑證定義的可匯出私密金鑰，並使用憑證嚮導將其指派給下列 Edge Server 外部介面：

<div>


> [!IMPORTANT]  
> Lync Server 不支援萬用字元憑證，除非用來匯總透過反向 proxy 的簡易 URLs。 您必須為部署所提供的每個 SIP 功能變數名稱、Web 會議 Edge service A/V Edge service 和 XMPP 網域，分別定義不同的主體替代名稱 (SANs) 。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 中引入，在目前憑證到期時間之前，暫存 Audio/Video 驗證憑證需要進行一些額外的規劃。 除了一個憑證的外部 Edge 介面具有多種用途之外，您還需要兩個憑證，一個憑證會指派給 Access Edge service 和 Web 會議 Edge service，另一個憑證用於 A/V Edge service。 如需詳細資訊，請參閱<A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">在 Lync Server 2013 中使用-擲入的暫存 AV 和 OAuth 憑證 Set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> 在邊際伺服器集區的事件中，您會將具有私密金鑰的憑證匯出至每個 Edge Server，並將憑證指派給每個 Edge Server 服務。 對內部 Edge Server 憑證執行相同的作業，並以私密金鑰匯出憑證，並指派給每個內部 Edge 介面。



</div>

  - 確定您已為憑證指派可匯出的私密金鑰

  - Access Edge service (稱為憑證嚮導中的「**外部 SIP 存取 Edge** 」) 

  - Web 會議 Edge service (稱為憑證嚮導中的「 **Web 會議 Edge 外部**」) 

  - A/V 驗證服務 (稱為憑證嚮導中的**A/V Edge 外部**) 

使用可匯出的私密金鑰建立單一的內部憑證，將其複製並指派給每個 Edge Server 內部介面：

  - Edge Server (稱為憑證嚮導中的**Edge Internal**) 

<div>


> [!IMPORTANT]  
> 您可以針對每個 Edge Server 服務使用不同且不同的憑證。 選擇個別憑證的最佳原因是您想要使用 A/V Edge service 憑證的新的「滾動憑證」功能。 在此項功能的情況下，建議將「Access Edge service」和「Web 會議 Edge service」的 A/V Edge service 憑證斷開。 如果您選擇要求、取得並指派各項服務的個別憑證，您必須為 A/V Edge service 要求私密金鑰可匯出 (，這實際上是 A/V 驗證服務) ，而且將相同的憑證指派給每台 Edge Server 上的 A/V Edge 外部介面。



</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中使用-滾 Set-CsCertificate 中的 AV 和 OAuth 憑證進行暫存](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Lync Server 2013 中影響 Edge Server 規劃的變更](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

