---
title: 將多個使用者移至試驗集區
description: 將多個使用者移至試驗集區。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 121509fbad863b0ce2d6cc9c7e9afaef360e2eb6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571329"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>將多個使用者移至試驗集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

您可以使用 Lync server 2013 控制台或 Lync Server 2013 管理命令介面，將多個使用者從 Lync Server 2010 集區移至 Lync Server 2013 試驗集區。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制台移動多位使用者

1.  開啟 [ **Lync Server 控制台**]。

2.  按一下 [ **使用者**]，按一下 [搜尋]，然後按一下 [ **尋找**]。

3.  選取兩個要移至 Lync Server 2013 集區的使用者。 在此範例中，我們會將使用者移 Chen 陽和聖誕老人聖誕 Hansen。
    
    ![將使用者移至特定的註冊集區](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "將使用者移至特定的註冊集區")  

4.  從 [ **動作** ] 功能表中，選取 [ **將選取的使用者移至集**區]。

5.  從下拉式清單中，選取 [Lync Server 2013 集區]。

6.  按一下 [動作]****，然後按一下 [將選取的使用者移至集區]****。 按一下 [確定]。
    
    ![移動使用者、目的地註冊集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者、目的地註冊集區] 對話方塊")  

7.  確認使用者的 [ **報名者集** 區] 欄現在包含 Lync Server 2013 集區，這表示使用者已順利移動。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面移動多位使用者

1.  開啟 [Lync Server 2013 管理命令介面]。

2.  在命令列上輸入下列命令，並將**User1**和使用者2取代為您想要移動的特定使用者名稱，並將**集區 \_ FQDN** **取代為目的地**集區的名稱。 在此範例中，我們會移動使用者 Hao Chen 和 Katie 約旦。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell Get-CsUser Cmdlet 的範例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-CsUser Cmdlet 的範例")  

3.  在命令列上輸入下列命令
    
        Get-CsUser -Identity "User1"

4.  **註冊機構集**區的身分識別現在應該指向您在上一個步驟中指定為**集區 \_ FQDN**的集區。 這個身分識別的出現表示已成功移動使用者。 重複步驟 **以驗證使用者2是否已移動** 。
    
    ![PowerShell Get-UsUser 識別指令程式的輸出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser 識別指令程式的輸出")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面同時移動所有使用者

在此範例中，所有使用者都已傳回 Lync Server 2010 集區 (pool01.contoso.net) 。 使用 Lync Server 2013 管理命令介面，我們會同時將所有使用者同時移至 Lync Server 2013 集區 (pool02.contoso.net) 。

1.  開啟 [ **Lync Server 2013 管理命令**介面]。

2.  在命令列輸入下列命令：
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![在管理命令介面中 PowerShell Cmdlet 及結果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "在管理命令介面中 PowerShell Cmdlet 及結果")  

3.  接下來，針對其中一位試驗使用者執行 **Get-CsUser** 。
    
        Get-CsUser -Identity "Hao Chen"

4.  每個使用者的 **註冊區集** 區身分識別，都指向您 \_ 在上一個步驟中指定為「集區 FQDN」的集區。 這個身分識別的出現表示已成功移動使用者。

5.  此外，我們可以在 Lync Server 2013 控制台中查看使用者清單，並確認 [註冊機集區] 值現在是否指向 Lync Server 2013 集區。
    
    ![Lync Server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制台使用者清單")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

