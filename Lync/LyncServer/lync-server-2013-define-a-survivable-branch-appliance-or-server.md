---
title: Lync Server 2013：定義 Survivable 分支裝置或伺服器
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
ms.openlocfilehash: ee83a532f3e378cf0beb0d9d09a08e935cf56247
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516370"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

如果您將 Survivable Branch Appliance 或 Server 加入拓撲時尚未予以定義，請在中央網站執行下列程序。

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>若要定義 Survivable 分支裝置或 Survivable 分支伺服器

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在主控台樹中，展開中央網站，展開 [ **分支網站**]，然後展開您計畫部署 Survivable branch 裝置或 Survivable branch 伺服器的分支網站名稱。

3.  以滑鼠右鍵按一下 [ **Survivable 分支裝置**]，然後按一下 [ **新增 Survivable Branch 裝置**]。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Survivable 分支裝置</STRONG> 是您用來定義 Survivable 分支伺服器和 Survivable 分支裝置的所在位置。

    
    </div>

4.  在 [ **定義 Survivable 分支裝置** ] 對話方塊中，按一下 [ **FQDN**]，然後輸入您要在此分支網站上部署之 Survivable Branch 裝置或 Survivable 分支伺服器的完整功能變數名稱 (FQDN) ，然後按 **[下一步]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您要定義 Survivable 分支裝置，您在 <STRONG>FQDN</STRONG> 中輸入的名稱，必須與您指派給 <STRONG>ServicePrincipalName</STRONG> 屬性的 Survivable 分支裝置 FQDN 相同。 如需詳細資訊，請參閱 <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch 裝置 To Active Directory In Lync Server 2013</A>。

    
    </div>

5.  按一下 [ **前端集**區]，在此 Survivable Branch 裝置或 Survivable branch 伺服器將要連線的中央網站上，按一下 [前端伺服器 (使用者服務集區) ]，然後按 **[下一步]**。

6.  按一下 [ **Edge Server**]，按一下此 Survivable branch 裝置或 Survivable branch 伺服器將要連線的 Edge 集區，以提供 PSTN 連線至分支網站的遠端使用者，然後按 **[下一步]**。

7.  按一下 [ **閘道 FQDN 或 IP 位址**]，然後輸入 Survivable Branch 裝置或 Survivable Branch Server 關聯的閘道對等機的 FQDN 或 IP 位址，以進行路由傳送撥入或撥出的 PSTN 通話。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您是在定義 Survivable Branch Appliance，此為 Survivable Branch Appliance 內之中繼伺服器將會連線以進行 PSTN 連線功能的閘道。

    
    </div>

8.  按一下 **[IP/PSTN 閘道的聆聽連接埠]**，接受預設連接埠。

9.  在 [ **Sip 傳輸通訊協定**] 中，按一下 [Survivable 分支裝置] 或 [Survivable] 分支伺服器將要使用的傳輸通訊協定，然後按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]  
    > 基於安全考量，強烈建議您使用傳輸層安全性 (TLS)。 如果您是在定義 Survivable Branch Appliance，請參閱您的 Survivable Branch Appliance 廠商文件，確認您的 Survivable Branch Appliance 支援 TLS 通訊協定。

    
    </div>

10. 在主控台樹狀目錄中，以滑鼠右鍵按一下新的 Survivable Branch Appliance 或 Server、按一下 **[拓撲]**，然後按一下 **[發行]**。

**後續步驟**：[使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器-分支網站](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)工作

</div>

</div>

<span> </span>

</div>

</div>

</div>

