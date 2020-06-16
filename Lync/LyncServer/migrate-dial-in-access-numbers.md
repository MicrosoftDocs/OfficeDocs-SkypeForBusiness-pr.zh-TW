---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 383fed15e2b67013ddd85356eb141a4c5dcf64e6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>移轉撥入存取號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

將撥入存取號碼從 Lync Server 2010 遷移至 Lync Server 2013 需要執行**Move-CsApplicationEndpoint** Cmdlet 以遷移連絡人物件。 在 Lync Server 2010 和 Lync Server 2013 共存期間內，您在 Lync Server 2013 中建立的撥入存取號碼，與您在 Lync Server 2010 中所建立的撥入存取號碼類似，如本節所述。

您在 Lync Server 2010 中建立的撥入存取號碼，但是會移至 Lync Server 2013，或在遷移期間或之後，您2013在遷移期間或之後所建立的撥入存取號碼具有下列特性：

  - 不會出現在 Office 通訊伺服器 2007 R2 會議邀請和撥入存取號碼頁面上。

  - 會出現在 Lync Server 2010 會議邀請和撥入存取號碼頁面上。

  - 會出現在 Lync Server 2013 會議邀請和撥入存取號碼頁面上。

  - 無法在 Office 通訊伺服器 2007 R2 系統管理工具中查看或修改。

  - 可在 Lync Server 2010 控制台和 Lync Server 2010 管理命令介面中查看及修改。

  - 可在 Lync Server 2013 控制台和 Lync Server 2013 管理命令介面中查看及修改。

  - 可以使用具有 Priority 參數的 Set-CsDialinConferencingAccessNumber Cmdlet，在地區內重新排序。

在解除委任 Lync Server 2010 集區之前，您必須完成指向 Lync Server 2010 集區的撥入存取號碼遷移。 如果您未完成撥入存取號碼遷移（如下列程式所述），則對存取號碼的來電將會失敗。

<div>


> [!IMPORTANT]  
> 您必須在解除委任 Lync Server 2010 集區之前執行此程式。



</div>

<div>


> [!NOTE]  
> 建議您在網路使用量很低時移動撥入存取號碼，以防出現短時間的服務中斷。



</div>

**識別並移動撥入存取號碼**

1.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要將每個撥入存取號碼移至主控于 Lync Server 2013 的集區，請從命令列執行：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  開啟 [Lync Server 控制台]。

4.  在左側導覽列中，按一下 **[會議]**。

5.  按一下 [**撥入存取號碼**] 索引標籤。

6.  確認您要遷移的 Lync Server 2010 集區中，是否仍然保留任何撥入存取號碼。
    
    <div>
    

    > [!NOTE]  
    > 當所有撥入存取號碼指向 Lync Server 2013 集區時，即可解除委任 Lync Server 2010 集區。

    
    </div>

**使用 Lync Server 控制台驗證撥入存取號碼遷移**

1.  從指派給**CsUserAdministrator**角色或**CsAdministrator**角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟 [Lync Server 控制台]。

3.  在左側導覽列中，按一下 **[會議]**。

4.  按一下 [**撥入存取號碼**] 索引標籤。

5.  確認所有撥入存取號碼都已遷移至 Lync Server 2013 上裝載的集區。

**使用 Lync Server 管理命令介面來驗證撥入存取號碼遷移**

1.  開啟 Lync Server 管理命令介面。

2.  若要傳回已遷移的所有電話撥入式會議存取號碼，請從命令列執行：
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  確認所有撥入存取號碼都已遷移至 Lync Server 2013 上主控的集區。

</div>

<span> </span>

</div>

</div>

</div>

