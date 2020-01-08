---
title: 將多個使用者移至 [試驗] 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ffc3e01df30f4a8e1b9c9b9aeca2b2013003980
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975919"
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

您可以使用 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]，將多個使用者從您的 Office 通訊伺服器 2007 R2 池中移至您的 Lync Server 2013 試驗區。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 [控制台] 移動多個使用者

1.  開啟 [ **Lync Server 控制台**]。

2.  從 [**使用者搜尋] 索引**標籤上，按一下 [**搜尋**] 按鈕。

3.  接著，按一下 [**新增篩選**]。

4.  建立 [ **Office 通訊伺服器] 使用者**等於 [ **True**] 的篩選器。

5.  按一下 [**尋找**]，搜尋舊版 Office 通訊伺服器 2007 R2 使用者。

6.  選取兩個您要移至 Lync Server 2013 池的使用者。 在這個範例中，我們會將使用者唐到 [陽入] 和 [Claus Hansen]。
    
    透過搜尋(images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "ocs 使用者所顯示")的 [![搜尋 ocs 使用者]] 使用者清單所顯示的使用者清單  

7.  從 [**動作**] 功能表中，選取 [**將選取的使用者移至資源庫**]。

8.  從下拉式清單中，選取 [Lync Server 2013] 池。

9.  按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。 按一下 [確定]。
    
    [![移動使用者]、[目的地註冊機構池] 對話方塊][(images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者]、[目的地註冊員池] 對話方塊")  

10. 確認使用者的 [**註冊機構池**] 欄現在包含 Lync Server 2013 池，這表示使用者已順利移動。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面來移動多個使用者

1.  開啟 Lync Server 2013 管理命令介面。

2.  在命令列中，輸入下列內容，並將 [ **User1** ] 和 [使用者 2] 替換為您想要**移動的特定**使用者名稱，並將 [**池\_FQDN** ] 取代為目的地池的名稱。 在這個範例中，我們會將使用者 Hao 唐和她約旦。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![移動舊版使用者](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "範例 Cmdlet 以移動舊版使用者")的範例 Cmdlet  

3.  在命令列中，輸入下列內容：
    
        Get-CsUser -Identity "User1"

4.  **註冊機構池**標識現在應該指向您在上一個步驟中指定為 [ ** \_池 FQDN** ] 的 [池]。 此身分識別的狀態會確認使用者已順利移動。 重複步驟**以驗證您**的操作2已移動。
    
    Powershell 取得![UsUser 身分識別 Cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "輸出的 Powershell UsUser 身分識別 Cmdlet")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面，同時移動所有使用者

在這個範例中，所有使用者都已回到 Office 通訊伺服器 2007 R2 pool （pool01.contoso.net）。 使用 Lync Server 2013 管理命令介面時，我們會同時將所有使用者移至 Lync Server 2013 池（pool02.contoso.net）。

1.  開啟**Lync Server 2013 管理命令**介面。

2.  在命令列中，輸入下列內容：
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![在 pool 範例 Cmdlet 中移動所有舊版使用者]以(images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "移動池中所有舊版使用者")的範例 Cmdlet  

3.  接下來，針對其中一個試驗使用者執行**move-csuser** 。
    
        Get-CsUser -Identity "Hao Chen"

4.  每個使用者的**註冊機構池**標識現在會指向您在上一個步驟中\_指定為 "pool FQDN" 的池。 此身分識別的狀態會確認使用者已順利移動。

5.  此外，我們還可以在 Lync Server 2013 的 [控制台] 中查看使用者清單，並確認 [註冊機構] 池值現在會指向 [Lync Server 2013] 池。
    
    ![Lync server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync server 2013 控制台使用者清單")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

