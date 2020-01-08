---
title: Lync Server 2013：將存檔資料庫新增至 Lync Server 2013 拓撲結構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe77c57050d6d6c70d5818405fd657d5a8fd3f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>將存檔資料庫新增到 Lync Server 2013 拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

您必須先將存檔納入拓撲中，才能設定您的部署支援封存。 本主題中的資訊說明如何使用拓撲建立器，將封存新增到您現有的拓撲。

<div>


> [!NOTE]  
> 如果您想要使用 Microsoft Exchange 整合來在 Exchange 2013 伺服器上為您的部署中的所有使用者儲存封存資料和檔案，請勿指定<STRONG>[封存 Sql server store</STRONG> ] 或<STRONG>[使用 SQL Server store 鏡像</STRONG>資訊]。



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>將封存資料庫支援新增到您的拓撲

1.  在執行 Lync Server 2013 或安裝 Lync Server 管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或具有同等使用者權限的帳戶）。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須將伺服器新增到拓撲中。您必須使用<STRONG>網域系統管理員</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組成員的帳戶，且在您用於 Lync server 2013 檔案存放區之檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立員可以設定必要的隨機存取控制清單（dacl）或具有同等權利的帳戶。

    
    </div>

2.  啟動拓撲建立器。

3.  在主控台樹中，流覽至您要在其中部署封存的 [前端] 池，然後按一下您要部署封存的 [前端] 池名稱。

4.  在 [**動作**] 功能表中，按一下 [**編輯屬性**]。

5.  在 [**編輯屬性**] 對話方塊中，按一下 **[一般**]。

6.  **向下滾動至 [** 封存]。

7.  選取 [**存檔**] 核取方塊。

8.  在 **[封存 SQL Server store** ] 底下，執行下列其中一項操作：
    
      - 若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。 如果您的所有使用者都是以 Microsoft Exchange Server 2013 或更高版本為宿主，您可以在 Exchange 中將所有使用者的 Lync 通訊封存。 在這種情況下，您不需要設定 SQL Server 封存存放區。
    
      - 若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：
        
          - 在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 存放區之伺服器的 FQDN。
        
          - 按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。
        
          - 如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。

9.  如果您想要使用 SQL Server store 鏡像，請選取 **[啟用 Sql Server store 鏡像**]，然後執行下列動作：
    
      - 若要使用現有的 SQL Server store 進行鏡像，請在 [封存**Sql server store** ] 下拉式清單方塊中，按一下您要用來進行鏡像的 SQL Server store 名稱。
    
      - 若要指定新的 SQL Server 存放區以進行鏡像，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列其中一項操作：
        
        1.  在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 sql server 存放區之 sql SERVER 的 FQDN。
        
        2.  按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。
        
        3.  如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。
    
      - 如果您啟用 SQL Server 鏡像，且想要包含 SQL Server 鏡像見證（第三個獨立的 SQL Server 實例，可偵測主要 SQL Server 服務器與鏡像實例的健康情況），請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊，然後執行下列其中一項操作：
        
        1.  在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 鏡像見證的伺服器 FQDN。
        
        2.  按一下 [**預設實例**] 以使用預設實例，或按一下 [指定**實例**]，然後指定您要用於鏡像見證的實例。
        
        3.  如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。

10. 若要儲存配置，請按一下 **[確定]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

