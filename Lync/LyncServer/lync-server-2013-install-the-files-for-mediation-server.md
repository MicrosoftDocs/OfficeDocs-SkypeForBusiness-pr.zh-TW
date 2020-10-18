---
title: Lync Server 2013：安裝轉送伺服器的檔案
description: Lync Server 2013：安裝轉送伺服器的檔案。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1fc20fb91328d116a4aee62b96b95aa3e270eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574069"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>在 Lync Server 2013 中安裝轉送伺服器的檔案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-06_

若要順利完成此程式，您應該至少以本機系統管理員身分登入伺服器，以及至少擁有 RTCUniversalReadOnlyAdmins 群組成員資格的網域使用者。

使用本主題中的步驟執行 Lync Server 2013 部署嚮導，在您使用拓撲產生器來定義及發行集區時，在您新增至轉送伺服器集區的電腦上，安裝轉送伺服器的檔案。 在安裝檔轉送伺服器時，您也會安裝並指派轉送伺服器集區中每一部電腦所需的憑證。

在此網站上，如果您已在前端集區或 Standard Edition server 上部署轉送伺服器組合，您可以略過本主題，而 [在 Lync server 2013 中](lync-server-2013-configuring-trunks.md)繼續設定主幹。

<div>


> [!NOTE]  
> 本主題假設您已定義及發佈獨立轉送伺服器集區，如在 <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Lync server 2013</A> 中的拓撲產生器中定義轉送伺服器和在部署檔 <A href="lync-server-2013-publish-the-topology.md">中發佈 lync server 2013 中的拓撲</A> 一節所述。而且，您已確認轉送伺服器集區中的電腦符合 lync Server 2013 中的 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">enterprise voice server 先決條件</A> 中所述的必要條件，以及 <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Lync server 2013 中 enterprise voice 的安全性和設定必要條件</A>。



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>若要為獨立的轉送伺服器集區安裝檔案

1.  在安裝媒體中，以滑鼠右鍵按一下 [ \<installation media\> ** \\ 安裝 \\ amd64 \\Setup.exe**]，然後按一下 [以**系統管理員身分執行**]。

2.  在 [ **安裝位置** ] 頁面上，按一下 **[確定]**。

3.  在 [ **使用者授權合約** ] 頁面上，按一下 [ **我接受**]，然後按一下 **[確定]**。 需要 (才能繼續。 ) 

4.  在 [ **Lync server 2010 部署嚮導]** 頁面上，按一下 [ **安裝或更新 Lync Server 系統**]。

5.  在 [ **步驟1：安裝本機設定存放區**] 旁邊，按一下 [ **執行**]，然後依照畫面上的指示進行。

6.  在 [ **設定中央管理存放區的本機複本** ] 頁面上，接受 **直接從中央管理存放區進行**的預設檢索，然後按 **[下一步]**。

7.  在 [ **執行命令** ] 頁面上，當工作狀態顯示為 [ **已完成**] 時，按一下 **[完成]**。

8.  在 [ **步驟2：安裝或移除 Lync Server 元件**] 旁邊，按一下 [ **執行**]，然後按 **[下一步]**。

9.  在 [ **執行命令** ] 頁面上，當工作狀態顯示為 [ **已完成**] 時，按一下 **[完成]**。

10. 在 [ **步驟3：要求、安裝或指派憑證**] 旁邊，按一下 [ **執行**]。 依照畫面上的指示，接受預設設定。 轉送伺服器需要一個憑證，因此您將執行 **步驟 3** 兩次：一次發出必要的憑證，再進行指派。

11. 當憑證已正確發行並指派正確時，在 [ **步驟4：啟動服務**] 旁邊，按一下 [ **執行**]，然後依照畫面上的指示進行。

12. 當 **步驟 4** 成功完成後，請重新開機伺服器，並以 DomainAdmins 群組成員的身分登入伺服器。

13. 在執行 Lync Server 控制台的電腦上，確認 [Lync Server 控制台] 的 [ **拓撲** ] 頁面上，轉送伺服器的服務狀態會顯示為綠色核取記號。 若改為顯示紅色 X，請選取轉送伺服器。 在 [ **動作** ] 功能表上，按一下 [ **啟動所有服務**]。

如果您已將一部以上的電腦新增至轉送伺服器集區，請在轉送伺服器集區中的所有其他電腦上，執行此程式中的步驟。 如果您不需要為其他任何電腦安裝轉送伺服器的檔案，請依照在 [Lync server 2013 中設定主幹中](lync-server-2013-configuring-trunks.md) 的程式來設定此轉送伺服器集區 (或所有轉送伺服器（位於網站) 及其對等）之間的主幹連接設定。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

