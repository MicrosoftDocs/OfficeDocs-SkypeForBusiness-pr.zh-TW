---
title: Lync Server 2013：設定檔案儲存
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
ms.openlocfilehash: 1bbb932a602ad1fc49907be9c5ab2777bc7a415f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>針對 Lync Server 2013 設定檔案儲存

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-05-23_

Lync Server 2013 支援在分散式檔案系統（DFS）上使用檔案共用。 如需有關 Windows server 2008 DFS 的詳細資訊，請參閱 Windows Server 2008 的 DFS 逐步指南[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)。若要使用 DFS，Lync Server 2013 需要下列專案：

  - 命名空間是以網域為基礎

  - 所有命名空間伺服器都執行了至少 Windows 2008

Lync Server 2013 安裝程式需要共用資料夾的許可權，才能擁有管理員的完整存取權。 接著 Lync Server 2013 會使用 NTFS 檔案許可權來為資料夾做為 ACL。 繼承的 DFS 共用許可權將不會用來限制存取權。

如需檔案共用需求的詳細資訊，請參閱支援檔中的[Lync Server 2013 檔案儲存支援](lync-server-2013-file-storage-support.md)。

<div>


> [!NOTE]  
> 您可能正在尋找有關設定非 DFS 共用的資訊。 如果是，請查看<A href="lync-server-2013-hardware-setup.md">Lync Server 2013 的硬體設定</A>。



</div>

下列程式說明如何使用 DFS 命名空間嚮導正確地設定共用資料夾的許可權（如 DFS 安裝指南中所述）。

<div>

## <a name="to-configure-shared-folder-permissions"></a>若要設定共用資料夾的許可權

1.  按一下 [**開始**]，指向 [**所有程式**]，指向 [系統**管理工具**]，然後按一下 [ **DFS 管理**]。

2.  在 [DFS 管理] 管理單元的 [主控台樹] 中，以滑鼠右鍵按一下命名空間伺服器（例如 filesrv1.contoso.com），然後按一下 [**編輯設定**]。

3.  選取 [**共用資料夾許可權**]。

4.  選取 [**使用自訂許可權**]。

5.  針對 [管理員] 群組，選取 [**允許**] 下的下列專案：
    
      - **完全控制**
    
      - **切換**
    
      - **查看**

6.  按一下 [套用]，**然後按一下** **[確定]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

