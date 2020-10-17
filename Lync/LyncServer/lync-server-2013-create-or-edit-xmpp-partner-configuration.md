---
title: Lync Server 2013：建立或編輯 XMPP 夥伴設定
description: Lync Server 2013：建立或編輯 XMPP partner configuration。
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
ms.openlocfilehash: 19289df1920287984f104bb1bdfa214d6f83f5cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553869"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中建立或編輯 XMPP partner configuration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-03_

Microsoft Lync Server 2013 整合了 Edge Server 上的可延伸訊息和顯示狀態通訊協定 (XMPP) proxy，以及前端伺服器或前端集區上的 XMPP 閘道。 若要允許來自其他 XMPP 部署的連線，您必須在 Lync Server 控制台中設定 XMPP。 您可以根據 XMPP 網域進行設定。 若要建立新的協力廠商關聯，您必須執行下列動作：

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>若要建立新的同盟合作夥伴或編輯現有的設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[同盟和外部存取]**，然後按一下 **[XMPP 同盟協力廠商]**。

4.  若要建立新設定，按一下 **[新增]**

5.  若要編輯現有的設定，可選取該設定，然後按一下 **[編輯]**

6.  若要建立或編輯 **[XMPP 同盟協力廠商]** 的設定，您要定義下列設定：

7.  **主要網域** (必要) 。 主要網域為 XMPP 協力廠商的基本網域。 例如，您可以為 XMPP 協力廠商網域名稱輸入 **fabrikam.com**。 此為必要項目。

8.  **描述**。 描述是針對此特定設定的附注或其他識別資訊。 此專案是選用專案。

9.  **其他網域**。 其他網域是 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。 例如，如果主域是 **fabrikam.com**，則您會列出位於 fabrikam.com 的所有其他網域，您會透過 XMPP 的方式來進行通訊。 例如，您可以在 fabrikam .com 的主要 XMPP 網域中，輸入公司 XMPP 網域和資訊技術 XMPP 網域的 **corp.fabrikam.com** 和 **it.fabrikam.com** 。

10. **合作夥伴類型**。 「 **合作夥伴類型** 」是必要的設定，可讓您選取下拉式功能表中的三個選項。 您必須選擇下列其中一項來描述及強制執行哪些連絡人可以新增。 您可以從下列選取：
    
      - **Federated**同盟。 同盟 **夥伴類型** 是 Lync Server 或 Office 通訊伺服器 2007 R2 協力廠商部署之間的信任連線。
    
      - **公用驗證**。 **公用驗證**夥伴是指可將提供者所驗證之部署之一部分的連絡人新增至使用者的連絡人清單。 可以從 Lync 使用者傳送邀請，或 Lync 使用者可以接受來自合作夥伴連絡人的邀請。
    
      - **公用未驗證**。 公開的未 **驗證** 關聯性表示兩個部署之間沒有建立且可驗證的狀態。 Lync 使用者必須邀請該連絡人的未驗證連絡人，才能將 Lync 使用者新增至其連絡人清單。 例如，Google GTalk 不是與 Lync Server 相關的公開驗證 XMPP 服務。 除非有從 Lync 使用者傳送的明確邀請，否則 GTalk 使用者將無法將 Lync 使用者新增為連絡人。

11. 關於資料流交涉與安全性方法傳輸層安全性 (TLS) 和軟體驗證及安全性階層 (SASL) 的附註：
    
    **XMPP Standards Foundation** (XSF) 和**網際網路工程任務推動小組** (IETF) 會定義一組使用與管理 TLS 用戶端憑證、TLS 伺服器憑證及 SASL 機制的規則與標準。使用 TLS 和 SASL 是保護 XMPP 資料流安全的必要程序。從 XMPP Standards 文件 **XEP-0178**，「指定建議使用的通訊協定流程，將 SASL EXTERNAL 機制與 PKIX 憑證搭配使用，特別是在 XMPP 服務指出 TLS 為強制交涉時。」PKIX (如 XSF 文件中所述) 是指公用金鑰基礎結構，亦稱為 PKI。
    
    如需 XMPP 需求的詳細資訊，請參閱 XSF 檔 XEP-0178。 如需詳細資訊，請參閱「XEP-0178：使用 SASL EXTERNAL with 憑證的最佳作法」。 <http://xmpp.org/extensions/xep-0178.html>
    
    請參閱 IETF 檔「可擴展郵件和顯示狀態通訊協定 (XMPP) ： Core」，5.0，STARTTLS 協商 <https://tools.ietf.org/html/rfc6120> 。
    
      - **TLS 協商**。 定義 TLS 協商規則。 XMPP 服務可以要求 TLS，也可以使用 tls 選用，或定義不支援 TLS。 選擇 [選用]，將需求留給 XMPP 服務，以強制進行必要的協商決策。 若要查看所有可能的設定和詳細資料，以瞭解 SASL、TLS 和回撥的協商-包括沒有有效和已知的錯誤設定，請參閱 [Lync Server 2013 中的 XMPP](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)同盟協力廠商協商設定。
        
          - <span></span>  
            **必要欄位**。 XMPP 服務要求 TLS 交涉。
        
          - <span></span>  
            **選用**。 XMPP 服務表示 TLS 為強制交涉。
        
          - <span></span>  
            **不支援**。 XMPP 服務不支援 TLS。
    
      - **SASL 協商**。 定義 SASL 協商規則。 XMPP 服務可能需要 SASL，可以進行 SASL 選用，或者您定義的是不支援 SASL。 選擇 [選用]，將需求留給夥伴 XMPP 服務，以進行強制協商決策。
        
        <div>
        

        > [!WARNING]  
        > SASL 要求 TLS。若要使用 SASL，TLS 必須是必要項目或選用項目。任何將 SASL 定義為必要或選用的設定都必須受到 TLS 支援。按一下 <STRONG>[認可]</STRONG> 以儲存您的變更時，如果您尚未將 TLS 設定為必要或選用，系統將會警告您，SASL 必須受到 TLS 支援，而您的變更將不會儲存。若要解決此錯誤，請將 TLS 設定為 <STRONG>[必要]</STRONG> 或 <STRONG>[選用]</STRONG>。如果 SASL 的用法為選用且無法支援 TLS 交涉，則您必須將 SASL 交涉設定為 <STRONG>[不支援]</STRONG>。利用 XMPP 服務來確認適用於 TLS 和 SASL 的正確交涉資料流必須是何種類型，或者將會發生服務中斷。

        
        </div>
        
          - <span></span>  
            **必要欄位**。 XMPP 服務要求 SASL 交涉。
        
          - <span></span>  
            **選用**。 XMPP 服務表示 SASL 為強制交涉。
        
          - <span></span>  
            **不支援**。 XMPP 服務不支援 SASL。
    
      - **回撥協商**。 回撥協商是由檔 XEP 中的 XSF 所定義 **-220：伺服器回撥** <http://xmpp.org/extensions/xep-0220.html> 。 伺服器回撥程式會使用網域名稱系統 (DNS) 和授權伺服器以驗證要求來自有效的 XMPP 合作者。 為做到這一點，始發伺服器會使用產生的回撥機碼來建立特定類型的郵件，並在 DNS 中查閱接收伺服器。 原始伺服器會將 XML 資料流程中的金鑰傳送到所產生的 DNS 查詢（大概是接收伺服器）。 當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。 授權伺服器會驗證機碼是否有效或無效。 如果無效，則接收伺服器不會回應始發伺服器。 若機碼是有效的，則接收伺服器會通知始發伺服器身分識別和金鑰是有效的，交談可以開始。
        
        **回撥交涉**具備兩種有效狀態：
        
          - <span></span>  
            **True**。 如果應該從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥協商。
        
          - <span></span>  
            **False**。 XMPP 伺服器並未設定為使用回撥交涉，而且，如果必須接收來自原始伺服器的要求，將會忽略此項

</div>

</div>

<span> </span>

</div>

</div>

</div>

