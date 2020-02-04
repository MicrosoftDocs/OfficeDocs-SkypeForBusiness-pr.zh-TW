---
title: Lync Server 2013：建立或編輯 XMPP 夥伴設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488665bca5cd2ad1b4d2d91a3c85a6a1ddaa3916
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中建立或編輯 XMPP 夥伴設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-03_

Microsoft Lync Server 2013 整合了 Edge 伺服器上的可擴展訊息和目前狀態通訊協定（XMPP） proxy，以及前端伺服器或頂層端池中的 XMPP 閘道。 若要允許來自其他 XMPP 部署的連線，您必須在 Lync Server [控制台] 中設定 XMPP。 您可以設定 XMPP 網域的設定。 若要建立新的合作夥伴關聯，請執行下列動作：

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>若要建立新的聯盟合作夥伴或編輯現有的配置

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**同盟及外部存取**]，然後按一下 [ **XMPP 聯盟夥伴**]。

4.  若要建立新的設定，請按一下 [**新增**]

5.  若要編輯現有的設定，請選取設定，然後按一下 [**編輯**]。

6.  若要建立或編輯**XMPP 聯盟夥伴**的設定，您可以定義下列設定：

7.  **主要網域**（必要）。 [主要網域] 是 XMPP 合作夥伴的基底網域。 例如，您可以輸入 XMPP 夥伴功能變數名稱的**fabrikam.com** 。 這是必要的專案。

8.  [**描述**]。 描述針對此特定設定的備忘稿或其他識別資訊。 這個專案是選用的。

9.  **其他網域**。 其他網域是您 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。 例如，如果主要網域是**fabrikam.com**，則您會列出位於 [fabrikam.com] 下的所有其他網域，您會透過 XMPP 進行通訊。 例如，您可能會在 [fabrikam .com 的主要 XMPP 網域] 下輸入公司 XMPP 網域的**corp.fabrikam.com**和**IT.FABRIKAM.COM** ，以及 XMPP domain 的資訊技術。

10. **合作夥伴類型**。 「**合作夥伴類型**」是必要的設定，可讓您選取下拉式功能表中的三個選項。 您必須選擇下列其中一項，以描述並強制加入您可以新增的連絡人。 您可以選取 [寄件者]：
    
      - **** 同盟。 **聯盟**夥伴類型是 Lync Server 或 Office 通訊伺服器 2007 R2 合作夥伴部署之間的信任連線。
    
      - **公用驗證**。 **公用驗證**合作夥伴是指由提供者驗證之部署的連絡人，可以新增至使用者的連絡人清單。 您可以從 Lync 使用者傳送邀請，或者 Lync 使用者可以接受來自合作夥伴連絡人的邀請。
    
      - **公用未驗證**。 **公用未驗證**的關聯表示兩個部署之間沒有已建立且可驗證的狀態。 Lync 使用者必須邀請該連絡人的未驗證連絡人，才能將 Lync 使用者新增至他的連絡人清單。 例如，Google GTalk 不是與 Lync Server 相關的公用驗證 XMPP 服務。 除非有明確的邀請從 Lync 使用者傳送，否則 GTalk 使用者將無法將 Lync 使用者新增為連絡人。

11. 資料流程協商和安全方法傳輸層安全性（TLS）及軟體驗證與安全性層（SASL）的注意事項：
    
    **XMPP 標準基礎**（XSF）和**網際網路工程工作組**（IETF）定義一組用來使用及管理 TLS 用戶端憑證、TLS 伺服器憑證及 SASL 機制的規則和標準。 使用 TLS 和 SASL 是保護 XMPP 資料流程所需的程式。 從 XMPP 標準檔**XEP-0178**，「指定建議的通訊協定流程，以使用包含 PKIX 憑證的 SASL 外部機制，尤其是當 XMPP 服務指出 TLS 是強制協商時。」 PKIX （如 XSF 檔所述），指的是公開金鑰基礎結構（也稱為 PKI）。
    
    如需 XMPP 需求的詳細資訊，請參閱 XSF 檔 XEP-0178。 如需詳細資訊，請參閱「XEP-0178：使用 SASL 外部與憑證的最佳做法」。 <http://xmpp.org/extensions/xep-0178.html>
    
    請參閱 IETF 檔「可擴展訊息和目前狀態通訊協定（XMPP）：核心」、5.0 區段、STARTTLS <http://tools.ietf.org/html/rfc6120>協商。
    
      - **TLS 協商**。 定義 TLS 協商規則。 XMPP 服務可能需要 TLS，可以進行 TLS 選用，或定義不支援 TLS。 選擇 [選用] 可將需求留給 XMPP 服務，以進行強制性的協商決策。 若要查看所有可能的設定和詳細資料，以瞭解 SASL、TLS 及回撥的協商，包括不合法和已知的錯誤配置-請參閱[Lync Server 2013 中 XMPP 聯盟夥伴的協商設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。
        
          - <span></span>  
            **必要**。 XMPP 服務需要 TLS 協商。
        
          - <span></span>  
            **選用**。 XMPP 服務指出 TLS 是強制性的協商式。
        
          - <span></span>  
            **不支援**。 XMPP 服務不支援 TLS。
    
      - **SASL 協商**。 定義 SASL 協商規則。 XMPP 服務可能需要 SASL、可進行 SASL 選擇，或定義不支援 SASL。 選擇 [選用] 可將需求留給合作夥伴 XMPP 服務，以進行強制性的協商決策。
        
        <div>
        

        > [!WARNING]  
        > SASL 需要 TLS。 若要使用 SASL，TLS 必須是必要的或選擇性的。 將 SASL 定義為 [必要] 或 [選擇性] 的任何設定，都必須有 TLS 支援。 按一下 [ <STRONG>Commit</STRONG> ] （提交）以儲存變更時，如果您未將 TLS 設定為 [必要] 或 [選擇性]，系統會在 SASL 必須提供 tls 支援，且不會儲存您所做的變更。 若要解決錯誤，請將 TLS 設定為 [<STRONG>必要</STRONG>] 或 [<STRONG>選擇性</STRONG>]。 如果您選用了 SASL，且無法進行 TLS 協商支援，則您必須將 SASL 協商設定為 [<STRONG>不支援</STRONG>]。 確認 XMPP 服務必須針對 TLS 和 SASL 進行哪些適當的協商資料流程，否則就會發生服務中斷。

        
        </div>
        
          - <span></span>  
            **必要**。 XMPP 服務需要 SASL 協商。
        
          - <span></span>  
            **選用**。 XMPP 服務指出 SASL 是必須協商的。
        
          - <span></span>  
            **不支援**。 XMPP 服務不支援 SASL。
    
      - **回撥（協商**）。 回撥的協商是由檔 XEP 中的 XSF 所定義 **-220：伺服器回撥** <http://xmpp.org/extensions/xep-0220.html>。 伺服器回撥程式會使用網域名稱系統（DNS）和權威性伺服器來驗證要求來自有效的 XMPP 合作夥伴。 若要這樣做，始發伺服器會使用產生的回撥金鑰來建立特定類型的郵件，並在 DNS 中尋找接收伺服器。 始發伺服器會將 XML 資料流程中的金鑰傳送到產生的 DNS 查詢（大概是接收伺服器）。 當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。 權威性伺服器驗證金鑰是否有效或無效。 如果無效，接收伺服器就不會回應始發伺服器。 如果金鑰有效，接收伺服器會通知始發伺服器：身分識別和金鑰有效，且可以開始交談。
        
        對於**回撥協商**，有兩種有效的狀態：
        
          - <span></span>  
            **True**。 如果應從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥的協商
        
          - <span></span>  
            **False**。 XMPP 伺服器未設定為使用回撥協商，如果應該從始發伺服器接收要求，則會被忽略

</div>

</div>

<span> </span>

</div>

</div>

</div>

