---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>移轉撥入存取號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

若要將電話撥入存取號碼從 Lync Server 2010 移植到 Lync Server 2013，必須執行**CsApplicationEndpoint** Cmdlet 來遷移連絡人物件。 在 lync Server 2010 和 Lync Server 2013 共存期間，您在 Lync Server 2013 中建立的撥入存取號碼與您在 Lync Server 2010 中建立的撥入存取號碼類似，如本節中所述。

您在 Lync Server 2010 中建立的撥入號碼，但移至 lync server 2013，或在遷移期間或之後，您在使用前或之後在 Lync Server 2013 中建立的電話：

  - 不會出現在 Office 通訊伺服器 2007 R2 會議邀請和 [撥入存取號碼] 頁面上。

  - 出現在 Lync Server 2010 會議邀請和 [撥入存取號碼] 頁面。

  - 出現在 Lync Server 2013 會議邀請和 [撥入存取號碼] 頁面。

  - 無法在 Office 通訊伺服器 2007 R2 管理工具中查看或修改。

  - 您可以在 Lync Server 2010 [控制台] 和 Lync Server 2010 管理命令介面中查看和修改。

  - 您可以在 Lync Server 2013 [控制台] 和 Lync Server 2013 管理命令介面中查看和修改。

  - 可在區域內使用 CsDialinConferencingAccessNumber Cmdlet 與 Priority 參數重新排序。

在您解除 Lync Server 2010 池之前，您必須先完成指向 Lync Server 2010 池的撥入存取號碼的遷移。 如果您沒有完成撥入存取號碼遷移，請參閱以下程式中所述的接入號碼來電將會失敗。

<div>


> [!IMPORTANT]  
> 您必須先執行此程式，然後才能解除 Lync Server 2010 池。



</div>

<div>


> [!NOTE]  
> 我們建議您在網路使用量較低時移動撥入存取號碼（如果有短暫的服務停機時間）。



</div>

**識別及移動撥入存取號碼**

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要將每個撥入存取號碼移至 Lync Server 2013 上託管的池中，請從命令列執行：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  開啟 [Lync Server 控制台]。

4.  在左側導覽列中，按一下 [**會議**]。

5.  按一下 [**撥入存取號碼**] 索引標籤。

6.  確認您要從中遷移的 Lync Server 2010 pool 不會保留撥入存取號碼。
    
    <div>
    

    > [!NOTE]  
    > 當所有撥入存取號碼都指向 Lync Server 2013 池時，您就可以解除 Lync Server 2010 池的授權。

    
    </div>

**使用 Lync Server [控制台] 驗證撥入存取號碼遷移**

1.  從指派給**CsUserAdministrator**角色或**CsAdministrator**角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟 [Lync Server 控制台]。

3.  在左側導覽列中，按一下 [**會議**]。

4.  按一下 [**撥入存取號碼**] 索引標籤。

5.  確認所有撥入存取號碼都已遷移至 Lync Server 2013 上託管的池中。

**使用 Lync Server 管理命令介面驗證撥入存取號碼遷移**

1.  開啟 Lync Server 管理命令介面。

2.  若要從命令列中傳回已轉移的所有電話撥入式會議存取電話號碼，請執行下列動作：
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  確認所有撥入存取號碼都已遷移至 Lync Server 2013 上託管的池中。

</div>

<span> </span>

</div>

</div>

</div>

