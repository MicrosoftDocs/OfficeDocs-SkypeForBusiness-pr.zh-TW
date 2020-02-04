---
title: Lync Server 2013：為 Director 設定憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fccab201ee9ab16b0195bc2780c37ab85f0519e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Director 的憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

<div>


> [!IMPORTANT]  
> 當您執行證書嚮導時，請確定您使用的帳戶是群組的成員，而該群組已獲指派您要使用之憑證範本類型的適當許可權。 根據預設，Lync Server 2013 證書要求會使用 Web 服務器憑證範本。 如果您使用的帳戶是 RTCUniversalServerAdmins 群組的成員，以使用此範本來申請憑證，請確認該群組已獲指派使用該範本所需的 [註冊] 許可權。



</div>

每個控制器都需要預設憑證、網頁內部憑證及網頁外部憑證。 如需控制器的憑證需求的詳細資料，請參閱規劃檔中的[Lync Server 2013 內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

使用下列程式來設定控制器憑證。 針對每個主管重複上述步驟。 此程式的步驟說明如何從貴組織部署的內部企業根憑證授權單位（CA）及離線要求處理來設定憑證。 如需從外部 CA 取得憑證的詳細資料，請與您的支援小組聯繫。

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>為主管或主管池設定憑證

1.  在 Lync Server 部署嚮導中，在 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**執行**]。

2.  在 [**憑證] 嚮導**頁面上，按一下 [**要求**]。

3.  在 [**憑證要求**] 頁面上，按一下 **[下一步]**。

4.  在 [**延遲] 或 [立即要求**] 頁面上，接受預設將**要求立即傳送給線上憑證授權單位**選項，然後按 **[下一步]**。

5.  在 [**選擇憑證授權單位（CA）** ] 頁面上，按一下您要使用的內部 Windows 憑證授權單位，然後按 **[下一步]**。

6.  在 [**認證機構帳戶**] 頁面上，指定您登入的帳戶沒有足夠的授權來要求憑證，然後按一下 **[下一步]**。

7.  在 [**指定備用憑證範本**] 頁面上，按一下 **[下一步]**。

8.  在 [**名稱及安全性設定**] 頁面上，您可以指定**易記名稱**、接受2048位金鑰長度，然後按 **[下一步]**。

9.  在 [**組織資訊**] 頁面上，選擇 [指定組織資訊]，然後按一下 **[下一步]**。

10. 在 [**地理資訊**] 頁面上，選擇 [指定地理資訊]，然後按 **[下一步]**。

11. 在 [ **Subject 名稱/Subject 替換名稱**] 頁面上，按一下 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > [Subject 替換名稱] 清單應包含您要安裝控制器的電腦名稱稱（如果是單一控制器）或主管池名稱，以及為組織設定的簡單 URL 名稱。

    
    </div>

12. 在 [**受領人替代名稱（san）** ] 頁面上的 [SIP 網域設定] 上，針對您想要讓控制器處理的所有網域，選取**已設定的 SIP 網域**，然後按一下 **[下一步]**。

13. 在 [**設定其他消費者備用名稱**] 頁面上，新增任何其他必要的消費者替換名稱，然後按 **[下一步]**。

14. 在 [**憑證要求摘要**] 頁面上，按一下 **[下一步]**。

15. 在 [**執行命令**] 頁面上，在命令執行完畢後，按一下 **[下一步]** 。

16. 在 [**線上憑證要求狀態**] 頁面上，按一下 **[完成]**。

17. 在 [**憑證指派**] 頁面上，按一下 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您想要查看憑證，請按兩下清單中的憑證。

    
    </div>

18. 在 [**憑證指派摘要**] 頁面上，按一下 **[下一步]**。

19. 在 [**執行命令**] 頁面上，在命令完成執行之後，按一下 **[完成]** 。

20. 在 [**憑證] 嚮導**頁面上，按一下 [**關閉**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

