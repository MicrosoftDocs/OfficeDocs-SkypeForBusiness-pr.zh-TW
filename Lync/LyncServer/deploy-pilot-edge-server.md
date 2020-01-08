---
title: 部署試驗 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd8fddd611422562c9384a52748623623d4e6f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982566"
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

本主題重點說明在部署 Lync Server 2013 Edge 伺服器之前，您應該注意的配置設定。 Lync Server 2013 的部署與設定處理常式與 Lync Server 2010 非常類似。 此區段只會醒目提示您要考慮的重要重點，做為您的試驗池部署的一部分。 如需詳細步驟，請參閱部署檔中的[Lync Server 2013 部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)（描述部署程式），同時提供外部使用者存取的設定資訊。

當您流覽 [**定義新的邊緣池**] 嚮導時，請參閱下列步驟中所示的 [金鑰設定] 設定。 請注意，只有幾頁會顯示 [**定義新的邊緣池**] 嚮導。

**定義邊緣池**

1.  登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。

2.  流覽至 Lync Server 2013 節點。 以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。
    
    ![[定義新的邊緣池] 對話方塊]會(images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "定義 [新增邊緣池] 對話方塊")

3.  Edge 池可以是**多個電腦池**或**單一電腦池**。
    
    ![定義 [邊緣池 fqdn] 對話方塊](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定義 [邊緣池 fqdn] 對話方塊")

4.  在 [**選取功能**] 頁面上，不要啟用同盟或 XMPP 同盟。 同盟與 XMPP 同盟目前是透過舊版 Lync Server 2010 Edge 伺服器路由。 這些功能將會在稍後的遷移階段進行設定。
    
    [![選取功能] 對話方塊]中的 [(images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "選取功能] 對話方塊")

5.  接著，繼續完成下列嚮導頁面：**外部 fqdn**、**定義內部 ip 位址**，以及**定義外部 ip 位址**。

6.  在 [**定義下一個躍點]** 頁面上，選取 Lync Server 2010 Edge 池下一個躍點的主管。
    
    ![[定義下一個躍點] 對話方塊](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "定義 [下一個躍點] 對話方塊")

7.  在 [**關聯前端或轉送池**] 頁面上，請勿在此時將池與此 Edge 池建立關聯。 外部媒體流量目前是透過舊版 Lync Server 2010 Edge 伺服器路由。 此設定將會在稍後的遷移階段進行設定。
    
    [![關聯前端池] 對話方塊][(images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "關聯前端池] 對話方塊")

8.  按一下 **[完成]** ，然後**發佈**拓撲。

9.  請依照部署檔中的[Lync Server 2013 安裝邊緣](lync-server-2013-install-edge-servers.md)伺服器中的步驟進行，以在新的 Edge 伺服器上安裝檔案、設定憑證，然後啟動服務。

在部署檔中，請遵循在[Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)主題中的準則，這一點非常重要。 本節僅提供安裝這些伺服器角色時設定設定的一些指導方針。

您現在應該會與 Lync Server 2013 Edge 伺服器部署並行部署舊版 Lync Server 2010 Edge 伺服器。 確認這兩個部署都能正常運作、服務已啟動，而且您可以在移至下一個階段之前管理每個部署。

</div>

<span> </span>

</div>

</div>

</div>

