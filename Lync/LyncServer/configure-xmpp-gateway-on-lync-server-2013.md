---
title: 在 Lync Server 2013 上設定 XMPP 閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87564835404928a79f9c61974d9581bba68069cd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40975094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>在 Lync Server 2013 上設定 XMPP 閘道

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-28_

遷移 XMPP 閘道的最後一個步驟是設定 Lync Server 2013 Edge 伺服器的憑證，部署 Lync Server 2013 XMPP Gateway，並更新 XMPP 閘道的 DNS 記錄。 這些步驟應並存執行，以最小化 XMPP 閘道的停機時間。 在執行這些步驟之前，必須先將所有使用者移至您的 Microsoft Lync Server 2013 部署。

<div class=" ">


> [!IMPORTANT]  
> 託管在 survivable 分支裝置上的使用者不支援 XMPP 同盟。 這適用于查看目前狀態資訊和交換 IM 訊息。



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>在 Lync Server 2013 Edge 伺服器上設定 XMPP 閘道憑證

1.  在 Edge 伺服器的 [部署嚮導] 中，在 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**再次執行**]。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果您是第一次部署邊緣伺服器，您會看到 [執行]，而不是再次執行。

    
    </div>

2.  在 [**可用的憑證**工作] 頁面上，按一下 [**建立新的憑證要求**]。

3.  在 [**憑證要求**] 頁面上，按一下 [**外部邊緣憑證**]。

4.  在 [**延遲] 或 [立即要求**] 頁面上，選取 [**立即準備要求，但稍後傳送**] 核取方塊。

5.  在 [**憑證要求**檔案] 頁面上，輸入要儲存申請之檔案的完整路徑和檔案名（例如，c：\\cert\_外部\_edge）。

6.  若要使用預設 Web 文件範本以外的範本，請在 [**指定備用憑證範本**] 頁面上，選取 [**針對所選的憑證授權單位使用替代憑證範本**] 核取方塊。

7.  在 [**名稱及安全性設定**] 頁面上，執行下列動作：
    
    1.  在 [**易記名稱**] 中，輸入憑證的顯示名稱。
    
    2.  在 [**位長**] 中，指定位長（通常是預設值2048）。
    
    3.  確認已選取 [將**憑證私人金鑰標示為可匯出**] 核取方塊。

8.  在 [**組織資訊**] 頁面上，輸入組織的名稱和組織單位（例如，部門或部門）。

9.  在 [**地理資訊**] 頁面上，指定位置資訊。

10. 在 [ **Subject 名稱/主旨替換名稱**] 頁面上，會顯示要由嚮導自動填入的資訊。 如果需要額外的消費者替換名稱，請在接下來的兩個步驟中加以指定。

11. 在 [**受領人替代名稱（san）** ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\> [主題替換名稱] 清單中的專案。

12. 在 [**設定其他消費者替換名稱**] 頁面上，指定任何所需的其他消費者替換名稱。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果已安裝 XMPP proxy，預設會在 SAN 專案中填入功能變數名稱（例如 [contoso.com]）。 如果您需要更多專案，請在此步驟中加以新增。

    
    </div>

13. 在 [**要求摘要**] 頁面上，查看要用來產生要求的憑證資訊。

14. 在命令完成執行之後，您可以**查看記錄**，或按一下 [下一步] 繼續。

15. 在 [**憑證要求**檔案] 頁面上，您可以按一下 [**查看**] 或 [結束證書] 嚮導來查看產生的憑證簽署要求（CSR）檔案，方法是按一下 **[完成]**。

16. 複製要求檔案並提交至您的公用憑證授權單位。

17. 接收、匯入及指派公用憑證之後，您必須停止並重新啟動 Edge 伺服器服務。 您可以在 Lync Server 管理主控台中輸入以下專案來執行此動作：
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>設定新的 Lync Server 2013 XMPP 閘道

1.  開啟 [Lync Server 控制台]。

2.  在左側導覽列中，按一下 [**同盟及外部存取**]，然後按一下 [ **XMPP 聯盟夥伴**]。

3.  若要建立新的設定，請按一下 [**新增**]。

4.  定義下列設定：

5.  **主要網域**    （必要）。 [主要網域] 是 XMPP 合作夥伴的基底網域。 例如，您可以輸入 XMPP 夥伴功能變數名稱的**fabrikam.com** 。 這是必要的專案。

6.  **描述**   針對此特定設定的備忘稿或其他識別資訊。 這個專案是選用的。

7.  **其他網域**   其他網域是您 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。 例如，如果主要網域是**fabrikam.com**，則您會列出位於 [fabrikam.com] 下的所有其他網域，您會透過 XMPP 進行通訊。

8.  **合作夥伴類型**   「**合作夥伴類型**是必要的設定。 您必須選擇下列其中一項，以描述並強制加入您可以新增的連絡人。 您可以選取 [寄件者]：
    
      - **** 同盟聯盟合作夥伴類型代表 Lync Server 部署與 XMPP 合作夥伴之間的高信任等級。 ****    我們建議使用此合作夥伴類型，以便與同一企業內的 XMPP 伺服器進行聯盟，或有已建立的業務關係。XMPP 聯盟夥伴中的連絡人可以：
        
        1.  新增 Lync 連絡人並查看其目前狀態（不需要 Lync 使用者的快速授權）。
        
        2.  無論 Lync 使用者是否已將立即訊息新增到連絡人清單中，都可以傳送立即訊息給 Lync 連絡人。
        
        3.  查看 Lync 使用者的狀態筆記。
    
      - **公用驗證**   **公用**XMPP 提供者是信任的公用提供者，可驗證其使用者的身分識別。在公開驗證的網路中 XMPP 連絡人可以新增 Lync 連絡人並查看其目前狀態，並在沒有 Lync 使用者的授權的情況下，傳送立即訊息給他們。在公開驗證的網路中 XMPP 連絡人，不會看到 Lync 使用者的狀態筆記。建議不要使用此設定。
    
      - **公用**驗證公用**合作夥伴是**不受信任的公用 XMPP 提供者，可驗證其使用者的身分識別。   除非 Lync 使用者已從連絡人清單中新增授權，否則，在公用未驗證的網路上 XMPP 使用者無法與 Lync 使用者通訊。XMPP 公用未驗證網路上的使用者永遠不會看到 Lync 使用者的狀態筆記。對於任何具有公用 XMPP 提供者的同盟（例如 Google 通話），建議使用此設定。

9.  **連線類型：** 定義各種規則與回撥設定。
    
      - **Tls 協商**   會定義 TLS 協商規則。 XMPP 服務可能需要 TLS，可以進行 TLS 選用，或定義不支援 TLS。 選擇 [選用] 可將需求留給 XMPP 服務，以進行強制性的協商決策。 若要查看所有可能的設定和詳細資料，以瞭解 SASL、TLS 及回撥的協商，包括不合法和已知的錯誤配置-請參閱[Lync Server 2013 中 XMPP 聯盟夥伴的協商設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。
        
          - <span></span>  
            **必要**   ： XMPP 服務需要 TLS 協商。
        
          - <span></span>  
            **選擇性**   ： XMPP 服務指出 TLS 是必須協商的。
        
          - <span></span>  
            **不支援**   XMPP 服務不支援 TLS。
    
      - **Sasl 協商**   會定義 SASL 協商規則。 XMPP 服務可能需要 SASL、可進行 SASL 選擇，或定義不支援 SASL。 選擇 [選用] 可將需求留給合作夥伴 XMPP 服務，以進行強制性的協商決策。
        
          - <span></span>  
            **必要需要**   SASL 協商的 XMPP 服務。
        
          - <span></span>  
            **選擇性**   ： XMPP 服務指出 SASL 是必須協商的。
        
          - <span></span>  
            **不支援**   XMPP 服務不支援 SASL。
    
      - **支援伺服器回撥回協商**支援伺服器回撥的協商程式會使用網域名稱系統（DNS）和權威性伺服器來驗證要求來自有效的 XMPP 合作夥伴。 若要這樣做，始發伺服器會使用產生的回撥金鑰來建立特定類型的郵件，並在 DNS 中尋找接收伺服器。 始發伺服器會將 XML 資料流程中的金鑰傳送到產生的 DNS 查詢（大概是接收伺服器）。 當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。 權威性伺服器驗證金鑰是否有效或無效。 如果無效，接收伺服器就不會回應始發伺服器。 如果金鑰有效，接收伺服器會通知始發伺服器：身分識別和金鑰有效，且可以開始交談。
        
        對於**回撥協商**，有兩種有效的狀態：
        
          - <span></span>  
            **True**   如果應從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥協商。
        
          - <span></span>  
            **False**   未將 XMPP 伺服器設定為使用回撥協商，而且如果應該從始發伺服器接收要求，則會被忽略。

10. 按一下 [**認可**]，儲存您對網站或使用者原則所做的變更。

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>更新 Lync Server 2013 XMPP 閘道的 DNS 記錄

1.  若要為 XMPP 同盟設定 DNS，您可以將下列 SRV 記錄新增到您的\_外部 DNS： XMPP-伺服器。\_tcp。\<[功能變數名稱] SRV 記錄會解析為邊緣伺服器的存取邊緣 FQDN，埠值為\> 5269。

</div>

</div>

<span> </span>

</div>

</div>

</div>

