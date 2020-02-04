---
title: 部署試驗 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 686973f9334b9bf376a2e56c52f3306cf243c0eb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>部署試驗 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

本主題重點說明在部署 Lync Server 2013 Edge 伺服器之前，您應該注意的配置設定。 此區段只會醒目提示您要考慮的重要重點，就像是您的試點邊緣池部署。 如需詳細步驟，請參閱部署檔中的[Lync Server 2013 部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)（描述部署程式），同時提供外部使用者存取的設定資訊。

當您流覽 [**定義新的邊緣池**] 嚮導時，請參閱下列步驟中所示的 [金鑰設定] 設定。 請注意，只有幾頁會顯示 [**定義新的邊緣池**] 嚮導。

**定義邊緣池**

1.  使用 [拓撲建立器] 開啟 [試驗] 泳池拓撲。

2.  流覽至 Lync Server 2013 節點。 以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。
    
    ![[定義新的 Edge 集區] 對話方塊](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊")

3.  Edge 池可以是**多個電腦池**或**單一電腦池**。
    
    ![[定義 Edge 集區 FQDN] 對話方塊](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[定義 Edge 集區 FQDN] 對話方塊")

4.  在 [**選取功能**] 頁面上，不要啟用同盟或 XMPP 同盟。 同盟與 XMPP 同盟目前是透過舊版 Office 通訊伺服器 2007 R2 Edge 伺服器路由。 這些功能將會在稍後的遷移階段進行設定。
    
    ![[選取功能] 對話方塊](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[選取功能] 對話方塊")

5.  接著，繼續完成下列嚮導頁面：**選取 [IP 選項**]、[**外部 fqdn**]、[**定義內部 Ip 位址**]，並**定義外部 ip 位址**。

6.  在 [**定義下一個躍點]** 頁面上，選取 Lync Server 2013 Edge 池下一個躍點的主管。
    
    ![[定義新的 Edge 集區] 對話方塊，下一個躍點集區清單](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊，下一個躍點集區清單")

7.  在 [**關聯前端池**] 頁面上，請勿在此時將池與此 Edge 池建立關聯。 外部媒體流量目前是透過舊版 Office 通訊伺服器 2007 R2 Edge 伺服器路由。 此設定將會在稍後的遷移階段進行設定。
    
    ![[定義新的 Edge 集區] 對話方塊](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊")

8.  按一下 **[完成]** ，然後**發佈**拓撲。

9.  請依照部署檔中的[Lync Server 2013 安裝邊緣](lync-server-2013-install-edge-servers.md)伺服器中的步驟進行，以在新的 Edge 伺服器上安裝檔案、設定憑證，然後啟動服務。

在部署檔中，請遵循在[Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)主題中的準則，這一點非常重要。 本節僅提供安裝這些伺服器角色時設定設定的一些指導方針。

您現在應該擁有舊版 Office 通訊伺服器 2007 R2 Edge 伺服器部署，並以與 Lync Server 2013 Edge 伺服器部署並行的方式來指示 BackCompatSite。 同盟已設定為使用 Office 通訊伺服器 2007 R2 控制器。 確認這兩個部署都能正常運作、服務已啟動，而且您可以在移至下一個階段之前管理每個部署。

![顯示 OCS Edge Server 的拓撲產生器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "顯示 OCS Edge Server 的拓撲產生器")

</div>

<span> </span>

</div>

</div>

</div>

