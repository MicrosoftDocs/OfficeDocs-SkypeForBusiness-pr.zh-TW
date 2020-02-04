---
title: Lync Server 2013：設定伺服器憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303724fa705fa94e9bbacacb4764bba7b918c460
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>在 Lync Server 2013 中設定伺服器憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-17_

若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入，或是委派正確的許可權。 如需委派許可權的詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。 根據您的組織和申請憑證的需求而定，您可能需要其他群組成員資格。 參閱管理公開金鑰基礎結構（PKI）憑證授權單位（CA）的群組。

<div>


> [!NOTE]  
> Lync Server 2013 包含對 SHA-1 套件的支援（SHA-1 是針對執行 Windows 7、Windows Server 512 R2、Windows Server 2008、Windows Vista 等用戶端的連線之摘要雜湊與簽名演算法的摘要長度，使用224、256、384或2008位）除了 Lync Phone Edition 之外，還有 Windows XP 作業系統。 若要使用 SHA-1 套件支援外部存取，外部憑證是由公用 CA 所頒發，也可以使用相同的位長度摘要來頒發憑證。



</div>

<div>


> [!WARNING]  
> 所選的雜湊摘要與簽章演算法取決於用戶端和要使用憑證的伺服器，以及用戶端與伺服器要與其通訊的其他電腦和裝置，也必須知道如何使用本文中所使用的演算法。憑證. 如需有關作業系統及一些用戶端應用程式支援哪些摘要長度的詳細資訊，<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>請參閱。



</div>

每個標準版伺服器或前端伺服器最多需要四個憑證： oAuthTokenIssuer 憑證、預設憑證、網頁內部憑證及網頁外部憑證。 不過，您可以使用適當的消費者替換名稱專案及 oAuthTokenIssuer 憑證來要求並指派單一預設憑證。 如需證書需求的詳細資訊，請參閱[Lync Server 2013 內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。 如需有關要求、指派及安裝 oAuthTokenIssuer 憑證的詳細資料，請參閱[在 Lync server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

使用下列程式來要求、指派及安裝標準版 server 或前端伺服器憑證。 針對每個前端伺服器重複上述步驟。

<div>


> [!IMPORTANT]  
> 下列程式說明如何從貴組織部署的內部企業 PKI 及離線要求處理來設定證書。 如需從公用 CA 取得憑證的相關資訊，請參閱規劃檔中的<A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 內部伺服器的憑證需求</A>。 此外，此程式也說明如何在設定前端伺服器期間要求、指派及安裝證書。 如果您提前要求證書，請參閱此部署檔的<A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 的 [提前申請憑證（選擇性）</A> ] 區段中所述，或者您不是使用貴組織中部署的內部企業 PKI 來取得憑證，您必須視情況修改此程式。



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>若要設定前端伺服器的憑證

1.  在 Lync Server 部署嚮導中，按一下**步驟3： [要求]、[安裝或指派憑證**] 旁的 [**執行**]。

2.  在 [**憑證] 嚮導**頁面上，按一下 [**要求**]。

3.  在 [**憑證要求**] 頁面上，按一下 **[下一步]**。

4.  在 [**延遲] 或 [立即要求**] 頁面上，您可以按一下 **[下一步]**，接受預設將**要求立即傳送給線上憑證授權單位**選項。 如果您選取此選項，則必須提供含自動線上註冊的內部 CA。 如果您選擇延遲要求的選項，系統會提示您輸入名稱和位置來儲存證書申請檔案。 證書申請必須由您組織內的 CA 或公用 CA 出示並處理。 接著您必須匯入憑證回應，然後將它指派給適當的憑證角色。

5.  在 [**選擇憑證授權單位（CA）** ] 頁面上，選取 [**從您的環境中偵測到的清單中選取 CA** ] 選項，然後從清單中選取 [已知] （透過 Active DIRECTORY 網域服務） CA 中的 [註冊]。 或者，選取 [**指定另一個憑證授權單位**] 選項，在方塊中輸入另一個 CA 的名稱，然後按 **[下一步]**。

6.  在 [**憑證授權單位帳戶**] 頁面上，系統會提示您輸入認證，以要求並處理 CA 的證書申請。 您應該已確定是否需要使用者名稱和密碼才能提前申請憑證。 您的 CA 管理員將會提供必要的資訊，而且可能必須在這個步驟中協助您。 如果您需要提供備用認證，請選取核取方塊，在文字方塊中提供使用者名稱和密碼，然後按一下 **[下一步]**。

7.  若要使用預設的 Web 服務器範本，請在 [**指定備用憑證範本**] 頁面上，按一下 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的組織已建立範本供您用來代替預設的 Web 服務器 CA 範本，請選取核取方塊，然後輸入備用範本的名稱。 您將需要由 CA 管理員所定義的範本名稱。

    
    </div>

8.  在 [**名稱及安全性設定**] 頁面上，指定可讓您識別憑證和用途的**易記名稱**。 如果您將它留白，系統會自動產生名稱。 設定金鑰的**位長**，或接受預設值2048位。 如果您認為需要將憑證和私人金鑰移動或複製到其他系統，請選取 [將**證書的私密金鑰標示為可匯出**]，然後按一下 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 對於可匯出的私密金鑰的需求最低。 其中一個位置是位於某個池中的邊緣伺服器上，媒體轉送驗證服務會使用憑證複本，而不是在池中每個實例的個別憑證。

    
    </div>

9.  在 [**組織資訊**] 頁面上，選擇 [提供組織資訊]，然後按一下 **[下一步]**。

10. 在 [**地理資訊**] 頁面上，選擇提供地理資訊，然後按 **[下一步]**。

11. 在 [**受領人名稱/主旨替換名稱**] 頁面上，查看將新增的 [subject 替換名稱]，然後按 **[下一步]**。

12. 在 [ **SIP 網域設定**] 頁面上，選取**SIP 網域**，然後按 **[下一步]**。

13. 在 [**設定其他消費者替換名稱**] 頁面上，新增任何其他必要的消費者替換名稱，包括將來其他 SIP 網域可能需要的任何其他主題，然後按 **[下一步]**。

14. 在 [**憑證要求摘要**] 頁面上，查看 [摘要] 中的資訊。 如果資訊正確無誤，請按 **[下一步]**。 如果您需要修正或修改設定，請按一下 [**返回**至正確的頁面]，以進行修正或修改。

15. 在 [**執行命令**] 頁面上，按一下 **[下一步]**。

16. 在 [**線上憑證要求狀態**] 頁面上，查看傳回的資訊。 您應該注意到證書已頒發並安裝到本機憑證存放區。 如果報告為已發出且已安裝，但無效，請確定 CA 根憑證已安裝在伺服器的根信任 CA 存放區中。 請參閱您的 CA 檔，瞭解如何檢索受信任的根 CA 憑證。 如果您需要查看檢索到的憑證，請按一下 [**查看憑證詳細資料**]。 根據預設，會選取 [**指派憑證至 Lync Server 證書使用**方式] 核取方塊。 如果您想要手動指派憑證，請清除該核取方塊，然後按一下 **[完成]**。

17. 如果您在前一頁清除 [**指派憑證至 Lync Server 證書使用**情況] 的核取方塊，就會顯示 [**憑證指派**] 頁面。 按一下 **[下一步]**。

18. 在 [**憑證存放區**] 頁面上，選取您要求的憑證。 如果您想要查看憑證，請按一下 [**查看憑證詳細資料**]，然後按一下 **[下一步]** 繼續。
    
    <div>
    

    > [!NOTE]  
    > 如果<STRONG>線上憑證要求狀態</STRONG>頁面報告了憑證的問題（例如憑證無效），請查看實際的憑證以協助解決問題。 可能導致憑證無法有效的兩個特定問題，就是先前提及的遺失根信任 CA 憑證，以及與憑證相關的遺失私密金鑰。 請參閱您的 CA 檔以解決這兩個問題。

    
    </div>

19. 在 [**憑證指派摘要**] 頁面上，查看所提供的資訊，以確認這是應該指派的憑證，然後按一下 **[下一步]**。

20. 在 [**執行命令**] 頁面上，檢查命令的輸出。 如果您想要查看作業程式，或是否已發出錯誤或警告，請按一下 [**查看記錄**]。 完成審閱後，請按一下 **[完成]**。

21. 在 [**憑證] 嚮導**頁面上，確認憑證的**狀態**為「已指派」，然後按一下 [**關閉**]。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 的憑證基礎結構需求](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

