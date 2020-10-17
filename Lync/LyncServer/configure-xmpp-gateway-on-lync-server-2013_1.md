---
title: 在 Lync Server 2013 上設定 XMPP 閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a2893d05230edbd261f7115a9be92bcd3275723
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503170"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>在 Lync Server 2013 上設定 XMPP 閘道

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

當您設定支援可延伸訊息和目前狀態通訊協定 (XMPP) 同盟協力廠商的原則時，這些原則會套用至 XMPP 同盟網域的使用者，但不會套用至工作階段初始通訊協定 (SIP) 立即訊息 (IM) 服務提供者 (例如 Windows Live) 或 SIP 同盟網域的使用者。 您可以為每個 XMPP 同盟網域設定所需的 XMPP 同盟協力廠商，以讓使用者新增連絡人並與連絡人通訊。 當原則就緒後，其他工作會包括設定 XMPP 閘道憑證、部署 Lync Server 2013 XMPP 閘道，最後更新 XMPP 閘道的 DNS 記錄。

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>在 Lync Server 2013 Edge Server 上設定 XMPP 閘道憑證

1.  在 Edge Server 的 [部署精靈] 中，按一下 [步驟 3: 要求、安裝或指派憑證]**** 旁邊的 [再執行一次]****。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果是第一次部署 Edge Server，則會看到 [執行]，而不是 [再執行一次]。

    
    </div>

2.  在 **[可用憑證工作]** 頁面上，按一下 **[建立新憑證要求]**。

3.  在 **[憑證要求]** 頁面上，按一下 **[外部邊緣憑證]**。

4.  在 **[延遲或立即要求]** 頁面上，選取 **[立即準備此要求，但稍後再傳送]** 核取方塊。

5.  在 [ **憑證要求** 檔案] 頁面上，輸入要儲存要求的檔案完整路徑和檔案名 (例如，c： \\ cert \_ 外部 \_ edge) 。

6.  若要使用預設 WebServer 範本之外的其他範本，請在 **[指定其他憑證範本]** 頁面上，選取 **[將其他憑證範本用於所選的憑證授權單位]** 核取方塊。

7.  在 **[名稱和安全性設定]** 頁面上，執行下列動作：
    
    1.  在 [易記名稱]**** 中，輸入憑證的顯示名稱。
    
    2.  在 [位元長度]**** 中，指定位元長度 (預設值通常是 2048)。
    
    3.  確認 [將憑證私密金鑰標示為可匯出]**** 核取方塊已經選取。

8.  在 **[組織資訊]** 頁面上，輸入組織的名稱和組織單位 (例如部門)。

9.  在 **[地理資訊]** 頁面上，指定位置資訊。

10. 在 **[主體名稱/主體別名]** 頁面上，會顯示精靈將自動填入的資訊。如果您還需要其他主體別名，請在後續兩個步驟中指定。

11. 在 [ **主體別名 (SANs) ** ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\> 專案的主體替代名稱清單。

12. 在 **[設定其他主體替代名稱]** 頁面上，指定任何需要的其他主體替代名稱。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果已安裝 XMPP Proxy，則 SAN 項目中預設會填入網域名稱 (例如 contoso.com) 。如果您需要更多項目，請在此步驟中新增它們。

    
    </div>

13. 在 **[要求摘要]** 頁面上，檢閱要用來產生要求的憑證資訊。

14. 當命令執行完畢之後，您可以 [檢視記錄檔]****，或按 [下一步]**** 繼續。

15. 在「憑證要求檔案」**** 頁面上，您可以按一下 [檢視] 檢視產生的憑證簽署要求 (CSR) 檔案，或按一下 [完成]**** 結束 [憑證精靈]。

16. 複製要求檔案，並送出到您的公用憑證授權單位。

17. 接收、匯入並指派公用憑證之後，您必須停止並重新啟動 Edge Server 服務。作法是輸入 Lync Server 管理主控台：
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>設定新的 Lync Server 2013 XMPP 閘道

1.  開啟 [Lync Server 控制台]。

2.  在左導覽列中，按一下 [同盟和外部存取]****，然後按一下 [XMPP 同盟協力廠商]****。

3.  若要建立新組態，請按一下 [新增]****。

4.  定義下列設定：

5.  **主要網域**     (必要) 。 主要網域為 XMPP 協力廠商的基本網域。 例如，您可以為 XMPP 協力廠商網域名稱輸入 **fabrikam.com**。 此為必要項目。

6.  **描述**    描述是針對此特定設定的附注或其他識別資訊。 此專案是選用專案。

7.  **其他網域**    其他網域是 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。 例如，如果主域是 **fabrikam.com**，則您會列出位於 fabrikam.com 的所有其他網域，您會透過 XMPP 的方式來進行通訊。

8.  **合作夥伴類型**    **同伴類型**是必要的設定。 您必須選擇下列其中一項來描述及強制執行哪些連絡人可以新增。 您可以從下列選取：
    
      - **Federated**同盟同盟**夥伴類型**代表 Lync Server 部署與 XMPP 合作夥伴之間的高信任層級。建議使用此夥伴類型，以與相同企業內的 XMPP 伺服器同盟，或已建立的業務關係。同盟合作夥伴中的 XMPP 連絡人可以：
        
        1.  新增 Lync 連絡人並檢視其目前狀態，而不需要 Lync 使用者的明確授權。
        
        2.  不論 Lync 使用者是否將 Lync 連絡人新增至其連絡人清單，都可將立即訊息傳送給 Lync 連絡人。
        
        3.  查看 Lync 使用者的狀態記事。
    
      - **公用驗證**  **公用驗證**夥伴是一種公開的 XMPP 提供者，可供信任以驗證使用者的身分識別。XMPP 公用驗證網路中的連絡人可以新增 Lync 連絡人並查看其目前狀態，並傳送立即訊息給他們，但不需要 Lync 使用者的明確授權。XMPP 公用驗證網路中的連絡人永遠不會看到 Lync 使用者的狀態筆記。建議您不要使用此設定。
    
      - **未公開驗證**：[未公開驗證]**** 協力廠商是無法確定其使用者身分識別之不受信任的公用 XMPP 提供者。除非 Lync 使用者將 [未公開驗證] 網路上的 XMPP 使用者新增至連絡人清單，以明確授權 XMPP 使用者，否則 [未公開驗證] 網路上的 XMPP 使用者無法與 Lync 使用者通訊。 [未公開驗證] 網路上的 XMPP 連絡人無法查看 Lync 使用者的狀態記事。若要與 Google Talk 等公用 XMPP 提供者進行任何同盟，建議使用此設定。

9.  **連線類型**：定義各種規則及回撥設定。
    
      - **TLS 協商**    定義 TLS 協商規則。 XMPP 服務可以要求 TLS，也可以使用 tls 選用，或定義不支援 TLS。 選擇 [選用]，將需求留給 XMPP 服務，以強制進行必要的協商決策。 若要查看所有可能的設定和詳細資料以進行 SASL、TLS 和回撥，請參閱[Lync Server 2013 中的 XMPP](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)同盟協力廠商協商設定。
        
           - **必要**    XMPP 服務需要 TLS 協商。
        
           - **選用**    XMPP 服務表示 TLS 必須協商。
        
           - **不支援**    XMPP 服務不支援 TLS。
    
      - **SASL 協商**    定義 SASL 協商規則。 XMPP 服務可能需要 SASL，可以進行 SASL 選用，或者您定義的是不支援 SASL。 選擇 [選用]，將需求留給夥伴 XMPP 服務，以進行強制協商決策。
        
           - **必要**    XMPP 服務需要 SASL 協商。
        
           - **選用**    XMPP 服務指出必須對 SASL 進行協商。
        
           - **不支援**    XMPP 服務不支援 SASL。
    
      - **支援伺服器的回撥協商** 支援伺服器回撥協商程式會使用網域名稱系統 (DNS) 和授權伺服器以驗證要求來自有效的 XMPP 合作者。 為做到這一點，始發伺服器會使用產生的回撥機碼來建立特定類型的郵件，並在 DNS 中查閱接收伺服器。 原始伺服器會將 XML 資料流程中的金鑰傳送到所產生的 DNS 查詢（大概是接收伺服器）。 當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。 授權伺服器會驗證機碼是否有效或無效。 如果無效，則接收伺服器不會回應始發伺服器。 若機碼是有效的，則接收伺服器會通知始發伺服器身分識別和金鑰是有效的，交談可以開始。
        
        **回撥交涉**具備兩種有效狀態：
        
           - **True**    如果應該從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥協商。
        
           - **False**    XMPP server 並未設定為使用回撥協商，而且若應該從始發伺服器接收要求，則會被忽略。

10. 按一下 [認可]**** 以儲存對網站或使用者原則的變更。

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>更新 Lync Server 2013 XMPP 閘道的 DNS 記錄

1.  若要設定 DNS 以進行 XMPP 同盟，您可以將下列 SRV 記錄新增至您的外部 DNS： \_ XMPP-server。 \_Tcp。\<domain name\> SRV 記錄會解析為 Edge server 的 Access Edge FQDN，埠值為5269。

</div>

</div>

<span> </span>

</div>

</div>

</div>

