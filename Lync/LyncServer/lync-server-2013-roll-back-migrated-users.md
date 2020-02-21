---
title: Lync Server 2013： 復原已移轉的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05678690718563dac9187ee275d3809016b78d33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>回復移轉 Lync Server 2013 中的使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-07_

如果您需要回復整合的連絡人存放區功能，，回復連絡人，只有當您將使用者移回至 Exchange 2010 或 Lync Server 2010。 若要回復，停用使用者的原則，然後執行 [ **Invoke-csucsrollback** cmdlet。 只執行**Invoke-csucsrollback**單獨不足以確保永久回復，因為如果原則未停用整合連絡人存放區移轉也會重新啟動。 例如，如果使用者復原，因為 Exchange 2013 會回復至 Exchange 2010 和使用者的信箱然後移至 Exchange 2013，整合連絡人存放區移轉將會被起始再次七天之後復原，只要整合的連絡人存放區仍維持啟用的使用者服務原則中的使用者。

<div>


> [!IMPORTANT]  
> <STRONG>Move-csuser</STRONG> cmdlet 會自動回復使用者的連絡人存放區從 Exchange 2013 到 Lync Server 2013 在下列情況： 
> <UL>
> <LI>
> <P>當使用者從 Lync Server 2013 移至 Lync Server 2010。</P>
> <LI>
> <P>當使用者是跨部署移轉，例如當使用者從移 Lync Online 至 Lync Server 2013 內部部署，反之亦然。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 從備份資料庫匯入整合連絡人存放區資料可能會導致整合連絡人存放區資料和損毀如果整合連絡人存放區模式變更之間匯出及匯入的使用者資料。 例如： 
> <UL>
> <LI>
> <P>如果您匯出連絡人清單，才能在使用者的連絡人移轉至 Exchange 2013，然後，在移轉後匯入相同的資料，但是整合連絡人存放區資料和連絡人清單就會損毀。</P>
> <LI>
> <P>如果您將使用者移轉至 Exchange 2013 之後，您可以匯出 userdata，回復移轉，然後從將資料匯入移轉後因任何原因，整合的連絡人存放區資料和連絡人清單就會損毀。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 您將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前，Exchange 系統管理員必須確定，Lync Server 系統管理員已先回復 Lync Server 使用者連絡人從 Exchange 2013 到 Lync Server。 若要將回復到 Lync Server 整合連絡人存放區連絡人，請參閱本節稍後的 < 對復原整合連絡人存放區連絡人從 Exchange 2013 to Lync Server 2013 中，「 程序。



</div>

下列程序說明如何回復使用者的連絡人。 如果您使用**Move-csuser** cmdlet 來 Lync Server 2013 和 Lync Server 2010 之間移動使用者時，因為**Move-csuser** cmdlet 會自動回復 unifed 連絡人存放區時它將使用者從 Lync Server 2013 移至 Lync Server 2010 可以略過這些步驟。 **Move-csuser**不讓移轉至整合連絡人存放區會循環，如果使用者移回至 Lync Server 2013 停用整合連絡人存放區原則。

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>將回復使用者連絡人從 Lync Server 2013 到 Lync Server 2010

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  停用回以便不被 remigrated rollback 之後復原使用者的整合連絡人存放區。 （執行這個步驟只有當您想要確保使用者將不會在未來的遷移時）。若要停用整合連絡人存放區針對個別使用者，請在命令列中輸入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  之前先從 Lync Server 2013 的使用者移至 Lync Server 2010 中，將回復朋友清單中所指定使用者的 Lync 伺服器上。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果省略這個步驟，將會遺失朋友清單。

    
    </div>

4.  回復為指定的使用者。 在命令列中輸入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 我們不建議使用-Force 參數來強制執行復原。 如果您使用此選項，將會遺失使用者的連絡人。

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>將回復整合連絡人存放區連絡人從 Exchange 2013 到 Lync Server 2013

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  停用回以便不被 remigrated rollback 之後復原使用者的整合連絡人存放區。 若要停用整合連絡人存放區針對個別使用者，請在命令列中輸入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  回復為指定的使用者。 在命令列中輸入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須先將回復 Lync Server 使用者]，然後再移 Exchange 2013 信箱。 Exchange 系統管理員會封鎖復原 Exchange，直到 Lync Server 復原已完成。 我們不建議使用-Force 參數來強制執行復原。 如果您使用此選項，將會遺失使用者的連絡人。

    
    </div>

4.  您將回復使用者到 Lync Server 之後，Exchange 系統管理員可以將回復 Exchange 使用者從 Exchange 2013 到 Exchange 2010。

</div>

</div>

<span> </span>

</div>

</div>

</div>

