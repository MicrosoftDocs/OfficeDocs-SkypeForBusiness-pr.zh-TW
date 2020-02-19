---
title: Lync Server 2013： 設定 DFS 檔案儲存空間
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8400d62560b1b599a7763f8582fd21da23e6948f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>設定 Lync Server 2013 的 DFS 檔案儲存空間

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-05-23_

Lync Server 2013 支援使用檔案共用上分散式檔案系統 」 (DFS)。 如需 DFS Windows Server 2008 的詳細資訊，請參閱 DFS 逐步指南的 Windows Server 2008 在[https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)。若要使用 DFS，Lync Server 2013 則需要下列項目：

  - 命名空間是以網域為基礎

  - 所有命名空間伺服器正在執行 Windows 2008 的最小值

Lync Server 2013 安裝程式需要共用資料夾的權限允許完整存取系統管理員。 Lync Server 2013 然後會使用 NTFS ACL 的檔案權限的資料夾。 繼承 DFS 共用權限不會用來限制存取。

如需關於檔案共用需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 中支援的檔案儲存空間](lync-server-2013-file-storage-support.md)。

<div>


> [!NOTE]  
> 您可能會尋找設定非 DFS 共用資訊。 如果是的話，請參閱<A href="lync-server-2013-hardware-setup.md">Lync Server 2013 的硬體設定</A>。



</div>

下列程序說明如何正確設定共用的資料夾權限 （如 DFS 安裝指南所述），使用 [DFS 命名空間精靈。

<div>

## <a name="to-configure-shared-folder-permissions"></a>若要設定共用的資料夾權限

1.  按一下 [**開始**、 指向 [**所有程式]**、 指向 [**系統管理工具**]，然後按一下 [ **DFS 管理**]。

2.  在 [DFS 管理] 嵌入式管理單元的主控台樹狀目錄中，命名空間伺服器 (例如 filesrv1.contoso.com)，以滑鼠右鍵按一下，然後按一下 [**編輯設定**。

3.  選取 [**共用資料夾權限**]。

4.  選取 [**使用自訂權限**。

5.  針對系統管理員群組中，選取 [**允許**] 下的下列：
    
      - **完全控制**
    
      - **變更**
    
      - **讀取**

6.  在 [**撥號對應表 (電話內容)**] 方塊中，按一下 [**瀏覽**] 以尋找使用者的撥號對應表。

</div>

</div>

<span> </span>

</div>

</div>

</div>

