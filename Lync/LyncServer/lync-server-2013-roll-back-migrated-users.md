---
title: Lync Server 2013：復原已移轉的使用者
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
ms.openlocfilehash: 5e8b8c53f835bbbaa363a91ef547dd1d301c8976
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>在 Lync Server 2013 中復原已移轉的使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

如果您需要回滾 [整合連絡人存放區] 功能，請只有在您將使用者移回 Exchange 2010 或 Lync Server 2010 時，才能回滾連絡人。 若要回滾，請停用使用者的原則，然後執行**CsUcsRollback** Cmdlet。 僅僅執行**Invoke CsUcsRollback**是無法確保永久復原，因為如果原則沒有停用，就會再次啟動整合式連絡人存放區遷移。 例如，如果使用者因為 Exchange 2013 已回滾至 Exchange 2010，且使用者的信箱移至 Exchange 2013，則在回滾之後的7天內就會再次開始進行整合連絡人商店遷移（只要整合連絡人存放區）在使用者服務原則中，仍已啟用使用者的。

<div>


> [!IMPORTANT]  
> 在下列情況下， <STRONG>move-csuser</STRONG> Cmdlet 會從 Exchange 2013 自動將使用者的連絡人存放區回滾至 Lync Server 2013： 
> <UL>
> <LI>
> <P>當使用者從 Lync Server 2013 移至 Lync Server 2010 時。</P>
> <LI>
> <P>使用者被遷移時（例如，當使用者從 Lync Online 移至 Lync Server 2013 內部部署時，或相反）。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 從備份資料庫匯入整合連絡人存放區資料時，如果在匯出與匯入之間變更了整合連絡人存放區模式，就會導致整合連絡人存放區資料和使用者資料遭到損毀。 例如： 
> <UL>
> <LI>
> <P>如果您先匯出連絡人清單，然後再將使用者的連絡人遷移至 Exchange 2013，然後在遷移之後，將相同的資料匯入，整合的連絡人商店資料和連絡人清單都會損毀。</P>
> <LI>
> <P>如果您在將使用者遷移至 Exchange 2013 之後匯出資料，請先回滾遷移，然後在遷移之後，在您匯入資料之後，整合連絡人商店資料和連絡人清單都會損毀。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 在將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前，Exchange 管理員必須先將 Lync Server 使用者連絡人從 Exchange 2013 回滾至 Lync Server。 若要將整合的連絡人存放區連絡人回滾至 Lync Server，請參閱本節稍後的程式「將整合的連絡人商店連絡人從 Exchange 2013 回滾至 Lync Server 2013」。



</div>

下列程式說明如何退回使用者連絡人。 如果您使用**move-csuser** Cmdlet 在 Lync server 2013 和 lync server 2010 之間移動使用者，您可以略過這些步驟，因為**move-csuser** Cmdlet 會在將使用者從 lync Server 2013 移至 lync server 2010 時，自動回滾 unifed 連絡人存放區。 **Move-csuser**不會停用整合式連絡人存放區原則，因此，如果使用者移回 Lync Server 2013，就會重複遷移至整合連絡人存放區。

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>從 Lync Server 2013 將使用者連絡人退回 Lync Server 2010

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  停用 [整合連絡人存放區]，讓使用者回滾之後就不會 remigrated。 （只有在您想要確保使用者在未來不會 remigrate 的情況下，才能執行此步驟）。若要停用個別使用者的整合連絡人存放區，請在命令列輸入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  在將使用者從 Lync Server 2013 移至 Lync Server 2010 之前，請先針對 Lync Server 上的指定使用者將好友清單回滾。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果省略此步驟，合作者清單將會遺失。

    
    </div>

4.  返回指定的使用者。 在命令列中，輸入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 我們不建議您使用– Force 選項來強制復原。 如果您使用這個選項，使用者的連絡人將會遺失。

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>若要將整合的連絡人存放區連絡人從 Exchange 2013 回滾至 Lync Server 2013

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  停用 [整合連絡人存放區]，讓使用者回滾之後就不會 remigrated。 若要停用個別使用者的整合連絡人存放區，請在命令列輸入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  返回指定的使用者。 在命令列中，輸入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須先退回 Lync Server 使用者，然後移動 Exchange 2013 信箱。 在 Lync Server 復原完成之前，Exchange 管理員會封鎖回退 Exchange。 我們不建議您使用– Force 選項來強制復原。 如果您使用這個選項，使用者的連絡人將會遺失。

    
    </div>

4.  當您將使用者回滾至 Lync Server 之後，Exchange 管理員就可以將 Exchange 使用者從 Exchange 2013 回滾至 Exchange 2010。

</div>

</div>

<span> </span>

</div>

</div>

</div>

