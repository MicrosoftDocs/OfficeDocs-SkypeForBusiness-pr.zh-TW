---
title: 移動多位使用者至試驗集區
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5616dd5fc48b90c52c2733802023385441c371d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>移動多位使用者至試驗集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

您可以將多個使用者與 Lync Server 2010 集區移至 Lync Server 2013 試驗集區使用 Lync Server 2013 Control Panel] 或 [Lync Server 2013 管理命令介面。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>若要使用 Lync Server 2013 Control Panel 移動多位使用者

1.  開啟**Lync Server 控制台**。

2.  按一下 [**使用者**]，按一下 [搜尋]，然後按一下 [**尋找**。

3.  選取您想要將移至 Lync Server 2013 集區的兩個使用者。 在這個範例中，我們會將使用者 Chen Yang 和聖誕老人 Hansen 移。
    
    ![將使用者移至特定註冊集區](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "將使用者移至特定註冊集區")  

4.  從 [**動作**] 功能表中，選取 [**移至集區選取的使用者**]。

5.  從下拉式清單中，選取 [Lync Server 2013 集區。

6.  按一下 [動作]****，然後按一下 [將選取的使用者移至集區]****。 按一下 [確定]。
    
    ![移動使用者，目的地登錄器集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者，目的地登錄器集區] 對話方塊")  

7.  請確認使用者的 [**登錄器集區**] 欄現在包含 Lync Server 2013 集區，即表示使用者已成功移動。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>若要使用 Lync Server 2013 管理命令介面時，移動多位使用者

1.  開啟 [Lync Server 2013 管理命令介面]。

2.  在命令列中，輸入下列命令，並使用您想要移動，並取代的特定使用者名稱取代**User1**和**User2** **集區\_FQDN**目的地集區的名稱。 在這個範例中我們將會移動 Hao Chen 和 Katie Jordan 的使用者。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell Get-csuser cmdlet 的範例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-csuser cmdlet 的範例")  

3.  在命令列上輸入下列命令
    
        Get-CsUser -Identity "User1"

4.  **登錄器集區**身分識別現在應指向您指定為集區**集區\_FQDN**在先前的步驟。 這個身分識別的出現表示已成功移動使用者。 重複步驟，以確認已移動**使用者 2** 。
    
    ![輸出的 PowerShell Get-UsUser 中-Identity 指令程式](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "輸出的 PowerShell Get-UsUser 中-Identity 指令程式")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>若要使用 Lync Server 2013 管理命令介面同時移動所有使用者

在這個範例中，所有使用者都回到 Lync Server 2010 集區 (pool01.contoso.net)。 使用 Lync Server 2013 管理命令介面，我們會將所有使用者同時都移至 Lync Server 2013 集區 (pool02.contoso.net)。

1.  開啟 [ **Lync Server 2013 管理命令介面**]。

2.  在命令列輸入下列命令：
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell cmdlet 與管理命令介面中的結果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet 與管理命令介面中的結果")  

3.  接著，執行**Get-csuser**為一位試驗使用者。
    
        Get-CsUser -Identity "Hao Chen"

4.  每位使用者的**登錄器集區**身分識別現在指向集區您指定為 「 集區\_FQDN 」 在先前的步驟。 這個身分識別的出現表示已成功移動使用者。

5.  此外，我們可以在 Lync Server 2013 Control Panel 中檢視的使用者清單，並確認登錄器集區值現在指向 Lync Server 2013 集區。
    
    ![Lync Server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制台使用者清單")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

