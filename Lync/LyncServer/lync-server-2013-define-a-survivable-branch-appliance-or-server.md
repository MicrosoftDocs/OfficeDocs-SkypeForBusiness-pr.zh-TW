---
title: Lync Server 2013：定義 Survivable Branch Appliance 或 Survivable Branch Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df5577ff0211afd005feb8fea4788598a03d536e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>在 Lync Server 2013 中定義 Survivable Branch Appliance 或 Survivable Branch Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

如果您沒有在將 Survivable 分支裝置或伺服器新增到拓撲時進行定義，請在中央網站執行此程式。

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>定義 Survivable 分支裝置或 Survivable 分支伺服器

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在主控台樹中，展開中央網站，展開 [**分支網站**]，然後展開您打算部署 Survivable 分支裝置或 Survivable 分支伺服器的分支網站名稱。

3.  以滑鼠右鍵按一下 [ **Survivable 分支裝置**]，然後按一下 [**新增 Survivable 分支裝置**]。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Survivable [分支裝置</STRONG>] 是您定義 Survivable 分支伺服器和 Survivable 分支裝置的位置。

    
    </div>

4.  在 [**定義 Survivable 分支裝置**] 對話方塊中，按一下 [ **FQDN**]，輸入您將在此分支網站上部署之 Survivable 分支裝置或 Survivable 分支伺服器的完整功能變數名稱（fqdn），然後按 **[下一步]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您是定義 Survivable 分支裝置，您在<STRONG>FQDN</STRONG>中輸入的名稱，必須與您指派給<STRONG>ServicePrincipalName</STRONG>屬性的 Survivable 分支裝置 FQDN 相同。 如需詳細資訊，請參閱<A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">在 Lync Server 2013 中新增 Survivable 分支裝置至 Active Directory</A>。

    
    </div>

5.  按一下 [**前端池**]，按一下此 Survivable 分支裝置或 Survivable 分支伺服器將連接的中央網站上的 [前端伺服器] （使用者服務池），然後按 **[下一步]**。

6.  按一下 [**邊緣伺服器**]，按一下這個 Survivable 分支裝置或 Survivable 分支伺服器將連接的邊緣池，以提供 PSTN 連線至分支網站的遠端使用者，然後按一下 **[下一步]**。

7.  按一下 [**閘道 FQDN] 或 [IP 位址**]，然後輸入 Survivable 分支裝置或 Survivable 分支伺服器與路由傳入或傳出 PSTN 通話關聯的閘道對等的 FQDN 或 ip 位址。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您是定義 Survivable 分支裝置，則這是 Survivable 分支裝置中的中繼伺服器將連接至 PSTN 連接的閘道。

    
    </div>

8.  按一下 [**偵聽埠（適用于 IP/PSTN）閘道**]，然後接受預設埠。

9.  在**Sip 傳輸通訊協定**中，按一下 Survivable 分支裝置或 Survivable 分支伺服器將使用的傳輸通訊協定，然後按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]  
    > 出於安全考慮，我們強烈建議您使用傳輸層安全性（TLS）。 如果您是定義 Survivable 分支裝置，請參閱 Survivable 分支裝置轉銷商檔，確認您的 Survivable 分支裝置支援 TLS 通訊協定。

    
    </div>

10. 在主控台樹中，以滑鼠右鍵按一下新的 Survivable 分支裝置或伺服器，按一下 [**拓撲**]，然後按一下 [**發佈**]。

**下一步**：[使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器-分支網站](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)工作

</div>

</div>

<span> </span>

</div>

</div>

</div>

