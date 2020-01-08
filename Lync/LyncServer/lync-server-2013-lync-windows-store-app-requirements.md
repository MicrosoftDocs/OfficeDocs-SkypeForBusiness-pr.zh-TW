---
title: Lync Server 2013： Lync Windows Store 應用程式需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806fb7a71232492be7ef01474136817b7808111e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Lync Server 2013 的 lync Windows Store 應用程式需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-03_

已部署 Lync Server 內部部署的組織必須符合下列需求才能支援 Lync Windows Store 應用程式。

<div>


> [!NOTE]  
> 針對 lync server 2010，請在所有伺服器上執行 lync server 2010 的累積更新：2月2012（適用于<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>）或更新版本。 若要讓使用者加入會議，請在伺服器上執行 Lync Server 2010 的累積更新：10月2012（可在<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>）。



</div>

  - 在伺服器上啟用 [自動探索]、[Lync Web App] 和 [Web 票證服務]。

  - 在前端伺服器或前端池中啟用憑證驗證。 （前端伺服器或前端池的使用者註冊程式通常稱為註冊機）。如需詳細資訊，請參閱[在 Lync Server 2013 中建立註冊機構配置設定](lync-server-2013-create-registrar-configuration-settings.md)。

  - 發佈自動探索服務的 DNS 別名（CNAME）資源記錄。

  - 您不再需要確認頒發給 Lync 伺服器的憑證的憑證吊銷清單（CRL）發佈點（CDP）指向 HTTP 資源，而不是 LDAP 資源。 不過，請確認用戶端電腦已安裝最新的 Windows 更新。

  - 在企業中設定 HTTP proxy，以允許 Lync server 相關的 HTTP 流量。如有需要，請為自動探索、Lync Web App 及 WebTicket 服務新增例外狀況。

  - 在用戶端上，安裝 Windows 8.1 和最新版本的 Lync Windows Store 應用程式，修正通常在使用多個網域時發生的登入問題（例如，SIP URI 是**userA@domainZ.com** ，而 Edge 伺服器是**sip.domainX.com**）。

如果您的組織訂閱 Lync Online 或 Office 365，而且您使用自己的功能變數名稱，您必須採取一些額外步驟來設定您的網路，以便在 Lync 伺服器中自動尋找。 Lync Windows Store app 與行動裝置上的 Lync 的網路設定需求相同。 請依照 Office 365 wiki 文章「設定 Lync 行動裝置」（位於）中的指示設定您的網路[http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822)。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中部署 Lync Windows Store 應用程式](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

