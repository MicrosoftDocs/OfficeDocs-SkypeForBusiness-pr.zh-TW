---
title: Lync Server 2013：退回遷移的使用者
description: Lync Server 2013：退回遷移的使用者。
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
ms.openlocfilehash: c5993bfd530c84307d3ee5be627b3ed33814be73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559539"
---
# <a name="roll-back-migrated-users-in-lync-server-2013"></a>在 Lync Server 2013 中復原已遷移的使用者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

如果您需要回復「整合連絡人存放區」功能，請僅在將使用者移回 Exchange 2010 或 Lync Server 2010 時，才復原連絡人。 若要回退，請停用使用者的原則，然後執行 **Invoke-CsUcsRollback** Cmdlet。 只執行 **Invoke-CsUcsRollback** 僅能確保永久復原，因為若未停用原則，將會再次啟動整合連絡人存放區遷移。 例如，如果使用者因為 Exchange 2013 復原回 Exchange 2010，而且使用者的信箱移至 exchange 2013，只要在使用者服務原則中仍為使用者啟用整合連絡人存放區，就會在復原後的七天內重新開始整合的連絡人存放區遷移。

<div>


> [!IMPORTANT]  
> 在下列情況下， <STRONG>Move-CsUser</STRONG> Cmdlet 會自動將使用者的連絡人存放區從 Exchange 2013 回復至 Lync Server 2013： 
> <UL>
> <LI>
> <P>當使用者從 Lync Server 2013 移至 Lync Server 2010 時。</P>
> <LI>
> <P>當使用者遷移跨單位部署時，例如，當使用者從 Lync Online 移至 Lync Server 2013 內部部署時，或相反。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 從備份資料庫匯入整合連絡人存放區資料可能會導致整合連絡人存放區資料和使用者資料在匯出與匯入間的統一連絡人存放區模式變更時損毀。 例如： 
> <UL>
> <LI>
> <P>如果您在將使用者的連絡人遷移至 Exchange 2013 之前匯出連絡人清單，然後在遷移後，匯入相同的資料，整合的連絡人存放區資料和連絡人清單會損毀。</P>
> <LI>
> <P>如果您在將使用者遷移至 Exchange 2013 之後匯出 userdata，請復原遷移，然後在遷移之後從某些原因匯入資料，整合的連絡人存放區資料和連絡人清單會損毀。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前，Exchange 管理員必須先確定 Lync server 系統管理員已先將 Lync Server 使用者連絡人從 Exchange 2013 復原至 Lync Server。 若要將整合連絡人存放區連絡人回復至 Lync Server，請參閱本節稍後的程式「將整合的連絡人存放區連絡人從 Exchange 2013 復原至 Lync Server 2013」。



</div>

下列程式說明如何退回使用者連絡人。 如果您使用 **Move-CsUser** 指令移動 lync server 2013 和 lync server 2010 之間的使用者，則可以略過這些步驟，因為 **Move-CsUser** Cmdlet 會在將使用者從 Lync Server 2013 移至 lync server 2010 時，自動將 unifed 連絡人存放區回退。 **Move-CsUser** 不會停用整合連絡人存放區原則，所以如果使用者移回 Lync Server 2013，就會重複遷移至整合連絡人存放區。

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>從 Lync Server 2013 退回使用者連絡人至 Lync Server 2010

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  停用整合連絡人存放區，讓使用者復原，這樣就不會在復原後 remigrated。 只有在您想要確保使用者今後不會 remigrate 的情況下，才執行此步驟。 ) 若要停用個別使用者的整合連絡人存放區，請在命令列中輸入： (
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  將使用者從 Lync Server 2013 移至 Lync Server 2010 之前，請回復 Lync Server 上指定使用者的好友清單。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果省略此步驟，好友清單將會遺失。

    
    </div>

4.  退回指定的使用者。 在命令列中輸入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 建議您不要使用– Force 選項強制復原。 如果您使用此選項，使用者的連絡人將會遺失。

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>若要將整合連絡人存放區連絡人從 Exchange 2013 復原至 Lync Server 2013

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  停用整合連絡人存放區，讓使用者復原，這樣就不會在復原後 remigrated。 若要停用個別使用者的整合連絡人存放區，請在命令列輸入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  退回指定的使用者。 在命令列中輸入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須先回復 Lync Server 使用者，然後移動 Exchange 2013 信箱。 在 Lync Server 復原完成之前，Exchange 系統管理員會封鎖回退 Exchange。 建議您不要使用– Force 選項強制復原。 如果您使用此選項，使用者的連絡人將會遺失。

    
    </div>

4.  在您將使用者復原至 Lync Server 之後，Exchange 管理員可以將 exchange 的使用者從 Exchange 2013 復原為 Exchange 2010。

</div>

</div>

<span> </span>

</div>

</div>

</div>

