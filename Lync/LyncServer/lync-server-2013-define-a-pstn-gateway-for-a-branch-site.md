---
title: Lync Server 2013：定義分支網站的 PSTN 閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a47e395e74dae1eb6ec454e63fb343dcea7872
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>在 Lync Server 2013 中定義分支網站的 PSTN 閘道

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

在中央網站（包含至少一個前端集區或 Standard Edition server）執行此程式。

<div>


> [!IMPORTANT]  
> 在執行此程式之前，必須先進行下列條件： 
> <UL>
> <LI>
> <P>Lync Server 2013 &nbsp; 通訊軟體必須在中央網站設定。</P>
> <LI>
> <P>轉送伺服器必須部署在中央網站。</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>若要定義 PSTN 閘道

1.  依序按一下 [**開始**]、[**所有程式**] 及 [ **Microsoft lync server**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在主控台樹中，展開中央網站，展開 [**分支 Office 網站**]，展開您要定義公用交換電話網路 (PSTN) 閘道的分支網站名稱，然後展開 [**共用元件**]。

3.  以滑鼠右鍵按一下 [PSTN 閘道]****，然後按一下 [新增 IP/PSTN 閘道]****。

4.  在 [**定義新的 IP/PSTN 閘道**] 對話方塊中，按一下 [**閘道 FQDN 或 IP 位址**]，然後輸入您要在分支網站上部署之閘道的完整功能變數名稱 (FQDN) 或 IP 位址。

5.  按一下 [ **IP/PSTN 閘道的聆聽埠**]，然後接受預設值。

6.  在 [ **SIP 傳輸通訊協定**] 清單中，按一下閘道使用的傳輸通訊協定，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 基於安全性的考慮，強烈建議您使用支援傳輸層安全性 (TLS) 的 PSTN 閘道。

    
    </div>

<div>


> [!TIP]  
> 使用 Cmdlet <STRONG>Set-CsPstnGateway</STRONG>修改 PSTN 閘道的屬性。 如需詳細資訊，請參閱 Lync Server Management Shell Help 中的<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>。



</div>

分支網站恢復功能的**下一個步驟**：[在 Lync Server 2013 中為分支網站恢復設定使用者](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的 PSTN 閘道部署選項](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

