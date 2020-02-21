---
title: 拓撲測試的 Lync Server 2013： 問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3e9b587a286cdff2b7ef08ec217a420792b121
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>在 [Lync Server 2013 拓撲測試的問題

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

**Test-cstopology**指令程式，例如最佳做法分析程式會提供方法，讓您確認 Lync Server 2013 正常運作的全域層級。 根據預設，最佳做法分析程式，例如指令程式，檢查整個的 Lync Server 2013 基礎結構，驗證，所需的服務正在執行，而且適當的使用者權利和權限有已設定這些服務和萬用當您安裝 Lync Server 2013 時，建立安全性群組。

除了驗證的 Lync Server 的整體有效性， **Test-cstopology**也可以檢查特定服務的有效性。 如需使用 cmdlet 來測試特定服務的詳細資訊，請參閱 Lync Server 管理命令介面文件中的[Test-cstopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 。 使用下列資訊有助於解決您拓撲的問題。

<div>


> [!NOTE]  
> 端視 Edge Server 以及任何相關周邊網路設定而定，包括防火牆設定和周邊，Best Practices Analyzer 可能無法存取和掃描 Edge Server。如果將 Edge Server 包含在掃描內，而且報告指出存取 Edge Server 發生問題，請清除 [Edge Server]<STRONG></STRONG> 核取方塊，並再次執行掃描，以避免問題出現在報告中。



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>解決拓撲的問題

如果拓撲測試發現拓撲的問題，這些問題可能是在您發行或啟用拓撲時發生的問題所造成。

變更拓撲時，變更在發行和啟用後才會生效。 您必須使用拓撲產生器] 可以變更拓樸。 您進行變更之後，接著可以發佈，並使用拓撲產生器中啟用這些變更。

當您發佈變更時，新的資訊 （例如，新的網站或新的伺服器角色） 會寫入至中央管理存放區。 不過，這些新物件 (或新修改的物件) 並不會立即加入您的拓撲中。 物件必須等到更新後的拓撲啟用後才會加入拓撲。 如果您選取 [發佈] 選項在拓撲產生器中兩個步驟進行： 所做的變更會發佈 (也就是說，它們會寫入中央管理存放區)，然後啟用新的拓撲。

根據預設，使用 RTCUniversalServerAdmins 群組的成員會獲授權執行**Publish-cstopology** cmdlet 及**Enable-cstopology** cmdlet。 不過，如果尚未委派設定權限，您必須登入以網域管理員的身分執行**Publish-cstopology**。 若要授與 RTCUniversalServerAdmins 實際使用**Publish-cstopology** cmdlet 的權限，您必須執行 Lync Server 服務的電腦包含每個 Active Directory 容器上執行**Grant-cssetuppermission** cmdlet。 若要授與 RTCUniversalServerAdmins 使用**Enable-cstopology** cmdlet 的權限，您必須針對執行 Lync Server 服務的電腦包含每個 Active Directory 網域服務容器執行**組 CsSetupPermission**指令程式。 請注意這適用於啟用和使用拓撲產生器發行拓撲。 如果您不具有使用**組 CsSetupPermission**委派權限，只是網域系統管理員可以啟用並發行拓撲，透過拓撲產生器]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

