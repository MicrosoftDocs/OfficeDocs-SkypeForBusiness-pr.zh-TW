---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaef027180304fca2a64294177faffcc0811e565
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>移轉撥入存取號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

從 Lync Server 2010 移轉的撥入存取號碼，以 Lync Server 2013 需要執行**Move-csapplicationendpoint** cmdlet 來移轉連絡人物件。 在 Lync Server 2010 和 Lync Server 2013 共存期間，您在 Lync Server 2013 中建立的撥入存取號碼的運作方式類似您在 Lync Server 2010 中建立的撥入存取號碼本節所述。

找出您在 Lync Server 2010 中建立，但已移至 Lync Server 2013 或期間或之後移轉之前，Lync Server 2013 中建立的撥入存取號碼具備下列特性：

  - 不會出現在 Office Communications Server 2007 R2 會議邀請及撥入存取號碼頁面。

  - 出現在 Lync Server 2010 會議邀請及撥入存取號碼頁面。

  - 出現在 Lync Server 2013 會議邀請及撥入存取號碼頁面。

  - 無法檢視或在 Office Communications Server 2007 R2 系統管理工具中修改。

  - 可檢視及修改 Lync Server 2010 控制台和以 Lync Server 2010 管理命令介面。

  - 可檢視及修改 Lync Server 2013 控制台和以 Lync Server 2013 管理命令介面。

  - 可以進行重新排序的區域內使用 Set-csdialinconferencingaccessnumber cmdlet 搭配 Priority 參數。

您必須完成移轉撥入存取號碼，指向 [Lync Server 2010 集區之前您解除委任 Lync Server 2010 集區。 如果您未完成下列程序所述撥入存取號碼移轉，將會失敗的存取號碼的傳入呼叫。

<div>


> [!IMPORTANT]  
> 您必須執行此程序在解除委任 Lync Server 2010 集區之前。



</div>

<div>


> [!NOTE]  
> 我們建議您在網路使用量較低，以防沒有在短時間內服務中斷時移動撥入存取號碼。



</div>

**識別及移動撥入存取號碼**

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  若要將每組撥入存取號碼移至 Lync Server 2013 上裝載的集區，從命令列執行：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  開啟 Lync Server 控制台。

4.  在左側導覽列中，按一下 **[會議]**。

5.  按一下 [**撥入存取號碼**] 索引標籤。

6.  不確認您要從中移轉的 Lync Server 2010 集區無任何撥入存取號碼。
    
    <div>
    

    > [!NOTE]  
    > 當所有撥入存取號碼都移至 Lync Server 2013 集區時，您即可解除委任 Lync Server 2010 集區。

    
    </div>

**撥入存取號碼使用驗證移轉的 Lync Server Control Panel**

1.  指派給**CsUserAdministrator**角色或**CsAdministrator**角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟 Lync Server 控制台。

3.  在左側導覽列中，按一下 **[會議]**。

4.  按一下 [**撥入存取號碼**] 索引標籤。

5.  確認所有撥入存取號碼均已移轉至 Lync Server 2013 上裝載的集區。

**撥入存取號碼使用驗證移轉的 Lync Server 管理命令介面**

1.  開啟 [Lync Server 管理命令介面]。

2.  若要傳回所有撥入式會議存取號碼移轉，從命令列執行：
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  確認所有撥入存取號碼將會都移轉至 Lync Server 2013 上裝載的集區。

</div>

<span> </span>

</div>

</div>

</div>

