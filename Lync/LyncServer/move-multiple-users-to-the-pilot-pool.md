---
title: 將多個使用者移至 [試驗] 池
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
ms.openlocfilehash: a8e347658d73405d7125eb439daff7eeb84e6ea7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>將多個使用者移至 [試驗] 池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

您可以使用 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]，將多個使用者從 Lync Server 2010 池中移至 Lync Server 2013 試驗區。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 [控制台] 移動多個使用者

1.  開啟 [ **Lync Server 控制台**]。

2.  按一下 [**使用者**]，按一下 [搜尋]，然後按一下 [**尋找**]。

3.  選取兩個您要移至 Lync Server 2013 池的使用者。 在這個範例中，我們會將使用者唐到 [陽入] 和 [Claus Hansen]。
    
    ![將使用者移至特定登錄器集區](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "將使用者移至特定登錄器集區")  

4.  從 [**動作**] 功能表中，選取 [**將選取的使用者移至資源庫**]。

5.  從下拉式清單中，選取 [Lync Server 2013] 池。

6.  按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。 按一下 [確定]。
    
    ![移動使用者，[目的地登錄器集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者，[目的地登錄器集區] 對話方塊")  

7.  確認使用者的 [**註冊機構池**] 欄現在包含 Lync Server 2013 池，這表示使用者已順利移動。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面來移動多個使用者

1.  開啟 Lync Server 2013 管理命令介面。

2.  在命令列中，輸入下列內容，並將 [ **User1** ] 和 [使用者 2] 替換為您想要**移動的特定**使用者名稱，並將 [**池\_FQDN** ] 取代為目的地池的名稱。 在這個範例中，我們會將使用者 Hao 唐和她約旦。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell Get-CsUser Cmdlet 的範例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-CsUser Cmdlet 的範例")  

3.  在命令列中，輸入下列內容：
    
        Get-CsUser -Identity "User1"

4.  **註冊機構池**標識現在應該指向您在上一個步驟中指定為 [ ** \_池 FQDN** ] 的 [池]。 此身分識別的狀態會確認使用者已順利移動。 重複步驟**以驗證您**的操作2已移動。
    
    ![PowerShell UsUser 身分識別 Cmdlet 的輸出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser -Identity Cmdlet 的輸出")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面，同時移動所有使用者

在這個範例中，所有使用者都已傳回 Lync Server 2010 pool （pool01.contoso.net）。 使用 Lync Server 2013 管理命令介面時，我們會同時將所有使用者移至 Lync Server 2013 池（pool02.contoso.net）。

1.  開啟**Lync Server 2013 管理命令**介面。

2.  在命令列中，輸入下列內容：
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![管理命令介面中的 PowerShell Cmdlet 與結果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "管理命令介面中的 PowerShell Cmdlet 與結果")  

3.  接下來，針對其中一個試驗使用者執行**move-csuser** 。
    
        Get-CsUser -Identity "Hao Chen"

4.  每個使用者的**註冊機構池**標識現在會指向您在上一個步驟中\_指定為 "pool FQDN" 的池。 此身分識別的狀態會確認使用者已順利移動。

5.  此外，我們還可以在 Lync Server 2013 的 [控制台] 中查看使用者清單，並確認 [註冊機構] 池值現在會指向 [Lync Server 2013] 池。
    
    ![Lync Server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制台使用者清單")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

