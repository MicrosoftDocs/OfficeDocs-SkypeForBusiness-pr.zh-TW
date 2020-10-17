---
title: Lync Server 2013： Lync Windows Store 應用程式需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3707c0074425411353a22b51d62251d33a4e31fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534600"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Lync Server 2013 的 lync Windows 應用程式需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-03_

具有 Lync Server 內部部署的組織必須符合下列需求，才能支援 Lync Windows Store 應用程式。

<div>


> [!NOTE]  
> 針對 Lync Server 2010，請執行 Lync Server 2010 的累計更新：2月 2012 (，可在<A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp 2670352</A>) 或更新版本的所有伺服器上執行。 若要讓使用者加入會議，請在伺服器上執行 Lync Server 2010：十月 2012 (的累計更新<A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; 3052&kbid = 2737915</A>) 。



</div>

  - 在伺服器上啟用自動探索、Lync Web App 及 Web 票據服務。

  - 在前端伺服器或前端集區上啟用憑證驗證。  (前端伺服器或前端集區上的使用者註冊程式通常稱為註冊機構。 ) 如需詳細資訊，請參閱 Create registration [configuration settings In Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)。

  - 針對自動探索服務，發佈 DNS 別名 (CNAME) 資源記錄。

  - 您不再需要確定憑證吊銷清單 (CRL) 發佈點)  (設定為 Lync server 指向 HTTP 資源的憑證，而不是 LDAP 資源。 不過，請確定用戶端電腦已安裝最新的 Windows 更新。

  - 設定企業中的 HTTP proxy，以允許 Lync server 相關的 HTTP 流量。如有必要，新增自動探索、Lync Web App 和 WebTicket 服務的例外狀況。

  - 在用戶端上，安裝 Windows 8.1 和最新版的 Lync Windows Store 應用程式，修正一般會在使用多個網域時發生的登入問題 (例如，當 SIP URI 是 **userA@domainZ.com** ，但 Edge Server 是 **sip.domainX.com**) 時。

如果您的組織訂閱 Lync Online 或 Microsoft 365，而且您使用自己的功能變數名稱，則必須採取一些額外的步驟來設定您的網路，以便自動探索 Lync 伺服器。 在行動裝置上，Lync Windows Store 應用程式和 Lync 的網路設定需求相同。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署 Lync Windows 應用商店應用程式](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
