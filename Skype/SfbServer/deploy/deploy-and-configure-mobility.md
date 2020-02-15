---
title: 部署及設定 Mobility skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文將引導您設定要使用的行動性服務，可讓您能夠利用 Skype for Business Server 行動功能的行動裝置現有 Skype for Business Server 安裝的步驟。
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029064"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>部署及設定 Mobility skype for Business Server  
 
本文將引導您設定要使用的行動性服務，可讓您能夠利用 Skype for Business Server 行動功能的行動裝置現有 Skype for Business Server 安裝的步驟。
  
需要檢閱[Mobility for Skype for Business Server 規劃](../plan-your-deployment/mobility.md)文章，您應該準備好繼續進行下列步驟來部署到您 Skype for Business 伺服器環境的行動性。 以下是步驟 （與我們正在此表格中包含的權限清單）：
  
|**階段**|**權限**|
|:-----|:-----|
|[建立 DNS 記錄](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[修改憑證](deploy-and-configure-mobility.md#ModCerts) <br/> |本機系統管理員  <br/> |
|[設定反向 Proxy](deploy-and-configure-mobility.md#ConfigRP) <br/> |本機系統管理員  <br/> |
|[使用混合式部署設定行動的自動探索](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[測試行動性部署](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[設定推入通知](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[設定行動性原則](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
下列各節包含步驟假設您已閱讀規劃主題。 如果任何項目令人困惑您，請隨意簽出所包含的資訊。

> [!NOTE]
> MCX (Mobility Service) 支援舊版的行動用戶端已不再提供 skype for Business Server 2019。 所有目前的 Skype for Business 行動用戶端已使用 Unified Communications Web API (UCWA) 來支援立即訊息 (IM)、 目前狀態和連絡人。 使用舊版用戶端使用 MCX 使用者必須升級至目前的用戶端。
  
## <a name="create-dns-records"></a>建立 DNS 記錄
<a name="CreateDNSRec"> </a>

您可能已經具備這些一部分您 Skype for Business Server 環境中，但您需要建立自動探索運作的下列記錄：
  
- 內部 DNS 記錄，以支援行動裝置正在從網際網路連接貴組織的網路內的使用者。
    
- 外部 （或公用） DNS 記錄支援行動裝置正在從網際網路連接您的組織網路外的使用者。
    
這些記錄可以是其中一個 A （主機） 名稱或 CNAME 記錄 （您不必使兩者，我們正在只包括步驟以下所有內容）。
  
### <a name="create-an-internal-dns-cname-record"></a>建立內部 DNS CNAME 記錄

1. 登入網路的**Domain Admins**群組成員或**DnsAdmins**群組中的 DNS 伺服器。
    
2. 按一下 [**啟動**] （您可能需要**搜尋**，如果它不是關閉 [開始] 功能表選項） 選擇**系統管理工具**]，然後按一下 [ **DNS** ] 以開啟 DNS 管理] 嵌入式管理單元。
    
3. 在主控台視窗的左側窗格中，您必須移至該網域的首頁您 skype for Business Server 前端伺服器，並依序展開 [**正向對應區域**那里。
    
4. 花些時間若要查看您有的下列其中一項：
    
   - 任何主機 A 或 AAAA 記錄您的前端伺服器 （Standard 或 Enterprise） 或前端集區。
    
   - 任何主機 A 或 AAAA 記錄為 Director 或 Director 集區 （選擇性的設定，您可能需要您部署中）。
    
5. 一旦您已記下此，您的 SIP 網域名稱上按一下滑鼠右鍵，然後從功能表中選擇 [**新別名 (CNAME)** 。
    
6. 在 [**別名名稱**] 文字方塊中，輸入 lyncdiscoverinternal 主機名稱，內部自動探索服務 url。
    
7. 在 [**完整的網域名稱 (目標主機的 FQDN**，您需要輸入或瀏覽至前端集區 （或單一前端伺服器，或 Director 集區或 Director），在上面的步驟 4 中識別的內部 Web 服務 FQDN。 這輸入時，請按一下 [確定]。
    
8. 您需要在您 Skype for Business Server 環境中支援的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。
    
### <a name="create-an-external-dns-cname-record"></a>建立外部 DNS CNAME 記錄

1. 這些步驟是通用的因為我們無法判斷您可能使用，哪些公用 DNS 提供者，但是我們仍要協助解決。請登入帳戶，將能夠讓新的 DNS 記錄有您公用 DNS 提供者。
    
2. 在目前，SIP 網域應該已經存在那里 skype for Business Server。 依序展開 [**正向對應區域**此 SIP 網域，或否則開啟它。
    
3. 花些時間若要查看您有的下列其中一項：
    
   - 任何主機 A 或 AAAA 記錄您的前端伺服器 （Standard 或 Enterprise） 或前端集區。
    
   - 任何主機 A 或 AAAA 記錄為 Director 或 Director 集區 （選擇性的設定，您可能需要您部署中）。
    
4. 一旦您有該資訊時，您應該可以選取 [建立**新別名 (CNAME)**] 選項。
    
5. 現在您應該能夠輸入**別名**，您需要輸入 lyncdiscover 以下外部自動探索服務 url。
    
6. 接下來應該區域，以輸入在 [**目標主機的 FQDN**，這必須是前端集區 （或單一前端伺服器，或 Director 集區或 Director），在步驟 3 上述中識別的 FQDN。
    
7. 您可能需要將儲存在這裡，或如果您需要在您 Skype for Business Server 環境中每個 SIP 網域的正向對應區域中建立額外 CNAME 記錄，您應該這麼做，但一旦您已準備就緒，儲存您的工作。
    
### <a name="create-an-internal-dns-a-record"></a>建立內部 DNS A 記錄

1. 登入網路的**Domain Admins**群組成員或**DnsAdmins**群組中的 DNS 伺服器。
    
2. 按一下 [**啟動**] （您可能需要**搜尋**，如果它不是關閉 [開始] 功能表選項） 選擇**系統管理工具**]，然後按一下 [ **DNS** ] 以開啟 DNS 管理] 嵌入式管理單元。
    
3. 在主控台視窗的左側窗格中，您必須移至該網域的首頁您 skype for Business Server 前端伺服器，並依序展開 [**正向對應區域**那里。
    
4. 花些時間若要查看您有的下列其中一項：
    
   - 任何主機 A 或 AAAA 記錄您的前端伺服器 （Standard 或 Enterprise） 或前端集區。
    
   - 任何主機 A 或 AAAA 記錄為 Director 或 Director 集區 （選擇性的設定，您可能需要您部署中）。
    
5. 一旦您已記下此，您的 SIP 網域名稱上按一下滑鼠右鍵，然後從功能表中選擇 [**新增主機 （A 或 AAAA）** 。
    
6. 在 [**名稱**] 文字方塊中，輸入 lyncdiscoverinternal 主機名稱，內部自動探索服務 url。
    
7. 在 [ **IP 位址**] 文字方塊中，上述步驟 4 中所識別類型您前端集區] （或單一前端伺服器，或 Director 集區或 Director） 的內部 Web 服務 IP 位址。
    
8. 完成時，請按一下 [**新增主機**]，然後按一下 [**確定]**。
    
9. 您需要在您 Skype for Business Server 環境中支援的每個 SIP 網域的正向對應區域中建立新的自動探索 A 或 AAAA 記錄。 若要這麼做，請重複步驟 6-8 為所需的次數。
    
10. 當您完成時，按一下 [**完成**]。
    
### <a name="create-an-external-dns-a-record"></a>建立外部 DNS A 記錄

1. 這些步驟是通用的因為我們無法判斷您可能使用，哪些公用 DNS 提供者，但是我們仍要協助解決。請登入帳戶，將能夠讓新的 DNS 記錄有您公用 DNS 提供者。
    
2. 在目前，SIP 網域應該已經存在那里 skype for Business Server。 依序展開 [**正向對應區域**此 SIP 網域，或否則開啟它。
    
3. 花些時間若要查看您有的下列其中一項：
    
   - 任何主機 A 或 AAAA 記錄您的前端伺服器 （Standard 或 Enterprise） 或前端集區。
    
   - 任何主機 A 或 AAAA 記錄為 Director 或 Director 集區 （選擇性的設定，您可能需要您部署中）。
    
4. 一旦您有該資訊，您應該可以選取 [建立**新的主機 A 或 AAAA**選項。
    
5. 現在您應該能夠輸入**名稱**，您需要輸入 lyncdiscover 以下外部自動探索服務 url。
    
6. 接下來應該區域，以在**IP 位址**中輸入，這必須是前端集區 （或單一前端伺服器，或 Director 集區或 Director），上述步驟 3 中所識別的 IP。
    
7. 您可能需要將儲存在這裡，或如果您需要建立其他 A 或 AAAA 記錄之每個 SIP 網域的正向對應區域的您 Skype for Business Server 環境，您應該這麼做，請但一次您已準備就緒，儲存您的工作。
    
## <a name="modify-certificates"></a>修改憑證
<a name="ModCerts"> </a>

如果您有關於規劃周圍憑證的問題，我們已經記錄，我們[Mobility for Skype for Business Server 規劃](../plan-your-deployment/mobility.md)文件中。 一旦您已檢閱所，我們將引導您完成下列：
  
- 是否需要新的憑證？
    
- 要求新憑證從憑證授權單位 (CA)。
    
- 使用 PowerShell 取代更新就地憑證。
    
- 檢查 Microsoft Management Console (MMC) 中使用 [憑證嵌入式管理單元的憑證。
    
### <a name="do-i-need-new-certificates"></a>是否需要新的憑證？

1. 首先，您可能需要檢查，並查看哪些憑證就地，並決定有您需要的項目。 若要這麼做，您需要使用具備本機系統管理員帳戶登入您 Skype for Business Server。 此帳戶可能也需要有權限若要發行的憑證授權單位 (CA)，其中某些步驟。
    
2. 開啟 Skype for Business Server 管理命令介面 （您可以使用搜尋找到它，如果您不需要它釘選到 [開始] 功能表中] 或 [工作] 列）。
    
3. 它會移至是不可或缺的要知道哪些憑證必須獲指派您嘗試加入已更新的憑證之前。 因此在命令中，輸入：
    
   ```powershell
   Get-CsCertificate
   ```

4. 步驟 3 中的資訊將會是您唯一的。 您要尋找它至判斷如果您有單一憑證已指派給多個項目，或是否有不同的憑證指派給需要之不同元件。 **使用**參數會告訴您如何使用的憑證，以及**Thumbprint**參數會告訴您如果是相同的所有憑證，或多個憑證。
    
5. 如果您有建議在我們的計劃] 區段的 SAN 項目，您已準備好。 如果不是，您必須從您的憑證授權單位要求新憑證或多個憑證 （根據您的設定）。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>要求新憑證或憑證，您的憑證授權單位 (CA)

1. 您已檢查，以查看您有哪些 SAN 項目之後，您會知道您有一個**單一憑證**（在檢查之後上述步驟透過），並學會您不需要您需要的所有項目。 新憑證要求，必須對您的 CA。 開啟您 Skype for Business Server PowerShell:
    
   - 針對遺漏自動探索服務 SAN (英文） （將-Ca 參數取代您自己的憑證授權單位的路徑）：
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 現在，如果您有多個 SIP 網域，您無法使用 AllSipDomain 參數，如上述範例所示。 您必須改為使用 DomainName 參數。 當您使用 DomainName 參數時，您已取得最新產品定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。 範例為 （將-Ca 參數取代您自己的憑證授權單位的路徑）：
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 或者，您已檢查，以查看您有哪些 SAN 項目之後，您找到您有**多個憑證**不具有您需要的所有項目。 新憑證要求，必須對您的 CA。 開啟您 Skype for Business Server PowerShell:
    
   - 針對遺漏自動探索服務 SAN (英文） （將-Ca 參數取代您自己的憑證授權單位的路徑）：
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 現在，如果您有多個 SIP 網域，您無法使用 AllSipDomain 參數，如上述範例所示。 您必須改為使用 DomainName 參數。 當您使用 DomainName 參數時，您已取得最新產品定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。 範例包括 （使用您自己的憑證授權單位路徑取代-Ca 參數）：
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - 一旦已經由 CA 所產生的新憑證，您要需要指派給他們。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>指派使用 Skype for Business Server 管理命令介面的憑證

- 根據所找到 [不要在我需要新上述的認證] 區段，您需要執行**一**項動作。
    
  - 如果您有單一憑證 （憑證碼皆相同） 的所有項目則您需要執行此程序：
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 如果您有不同的憑證 （憑證碼為完全不同） 中的物件，請改為這執行：
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>檢視憑證在 Microsoft Management Console (MMC)

1. 您可以選擇来查看您使用 [憑證嵌入式管理單元 MMC 的憑證。 只是將搜尋輸入 MMC，它應該 pop 為應用程式] 選項。
    
2. 若要新增 [憑證嵌入式管理單元，您需要按一下 [**檔案**]，然後**新增/移除嵌入式管理單元-英吋..** （或鍵盤快速鍵**Ctrl + M**也可以運作）。 **憑證**會是在左窗格中的選項，請在快顯視窗，然後**下一步**中選取它，然後**電腦帳戶**。
    
3. 仍在快顯視窗中，在所有的可能性您正在執行此動作具有首頁需的憑證，以查看，因此請保持到**本機電腦**上選取範圍如果是這樣的電腦上。 如果您正在遠端電腦上，變更為**另一部電腦**的 [選項] 按鈕，然後輸入該電腦的 FQDN 或使用 [**瀏覽**] 按鈕來搜尋 AD 透過該電腦。 選取之電腦之後, 您需要按一下 [**完成**]，準備好時，然後 **[確定]** 嵌入式管理單元新增至 MMC。
    
4. 依序展開 [**憑證**] 區段中，在 MMC 的左窗格中。 展開 [**個人**] 資料夾，然後再選取 [**憑證**。 這可讓您查看此存放區中的憑證。
    
5. 您需要找出您想要檢視，請將憑證上按一下滑鼠右鍵，然後選擇 [**開啟**。
    
    > [!NOTE]
    > 您要如何知道這是什麼憑證？ 它應該是指派給每個伺服器陣列，項目可以是單一憑證或您可能會有不同的項目，例如預設、 內部 Web 服務等的多個憑證，在這種情況下，您可能需要查看多個憑證。 多個憑證會有相同的憑證指紋。 
  
6. 一旦您已取得至 [**憑證**] 檢視，選擇 [**詳細資料**。 這可讓您查看憑證主體名稱，當您選取**主旨**，並會顯示指派的主體名稱及相關聯的內容。
    
7. 您也需要檢查的**主體替代名稱**項目。 您會發現下列一或多個動作：
    
   - 此集區的集區名稱或單一伺服器名稱，如果這不是集區。
    
   - 將憑證指派給伺服器名稱。
    
   - 簡單 URL 記錄，通常為 meet 和 dialin。
    
   - Web 服務內部和 Web 服務外部名稱 （例如，webpool01.contoso.net、 webpool01.contoso.com），根據所做的選擇在拓撲產生器和覆寫的 Web 服務選擇而定。
    
   - 如果已經指派，lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄。
    
     您需要檢查多個憑證，如果您有多個指派 （檢查上面的附註）。
    
8. 因此，如果您發現 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄，您是否已取得最新產品這已設定。 您可以關閉 [MMC。
    
9. 如果未指派給他們，則需要進行新的憑證要求 （上面所述） 或您需要進行安裝後的要求 (我們建議下列 PowerShell 上方，)。
    
## <a name="configure-the-reverse-proxy"></a>設定反向 Proxy
<a name="ConfigRP"> </a>

下列步驟並不代表完全後面。 這是產品的因為在舊版，我們會受到您透過，例如設定 Threat Management Gateway (TMG)，且如果您未使用的您必須找出您自己從該處的版本。
  
TMG 不再提供是由 Microsoft 產品中，為，如果您仍然需要將其設定，您可以查看[Lync Server 2013 的步驟](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)。 但是，下列資訊的目的是更通常有幫助，即使沒有我們可以提供特定的逐步解說步驟剔除有每個反向 proxy 的方法。
  
我們有兩個主要的考量事項：
  
- 您進行初始自動探索要求 over HTTPS （其中建議使用）？
    
  - 如果您有 web 發行規則，您需要對其進行修改。
    
  - 如果您沒有 web 發行規則，您必須建立它。
    
- 如果您透過 HTTP 進行初始自動探索要求，您將需要建立或修改該規則也。
    
> [!NOTE]
> **重要**Proxy 逾時值是而部署的數字。 您應該監視您的部署，並修改用戶端的最佳體驗的值。 您可以將值設定為 200。 如果您要支援 Lync 行動用戶端環境中，您應該 960 可用於推入通知逾時設定從 Office 365 有 900 的逾時值設定值。 很有可能需要增加以避免用戶端的逾時值中斷連線時的值是太低，或如果通過 proxy 的連線，請不要中斷，但清除長時間後已中斷連線的用戶端減少數目。 監視及基準為何平常為您的環境是只精確的方法來決定適當的設定，此值。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>修改現有的 web 發行規則外部自動探索 SAN 及 URL

1. 開啟您的反向 proxy 介面。
    
2. 您需要找出您的 web 發行規則，並選擇 [編輯] 選項 （可能為功能表或根據您的反向 proxy 設定] 索引標籤）。
    
3. 應該會指出這個網頁發行規則會套用至某個區域。 您要修改此規則的連入的網站的要求。 您要**新增**新的項目。
    
4. 輸入您網站的名稱自動探索 （我們將使用此範例會為 lyncdiscover.contoso.com），然後按一下 **[確定]** 或 [**儲存**，根據您的反向 proxy 的格式。
    
5. 您可能需要新的憑證中有自動探索 SAN 項目。 需要一併安裝和設定用於根據您的反向 proxy 設定。 請務必先完成組態時儲存所有項目。
    
6. 如果您的反向 proxy 已**測試**的功能，請使用它來確定一切正常運作。
    
7. 現在，您可能需要重複這些步驟，如果您有 Director 或 Director 集區中您的環境 （這表示您有第二個規則）。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>外部自動探索 url 建立 web 發行規則

1. 開啟您的反向 proxy 介面。
    
2. 您需要找出其中介面中您建立網頁發行規則，並選擇 [**新增**] 或 [**建立**] 選項 （可能為功能表或根據您的反向 proxy 設定] 索引標籤）。 您要尋找要建立新的 web 發行規則的選項。
    
3. 一般而言，您需要輸入下列資訊：
    
   - **名稱**： 您的規則的名稱
    
   - **規則動作**： 在此情況下是**允許**規則，就會讓通過反向 proxy 的某個項目。
    
   - 您選擇的**發佈**規則或選項就是**單一網站或負載平衡器**。
    
   - 這必須是**SSL**進行外部存取，請選擇該選項。
    
   - 您將需要發佈**內部發佈**，路徑，並輸入 FQDN，才在前端集區的負載平衡器 （或 FQDN，Director 集區的負載平衡器如果有的話） 的外部 Web 服務，就是 sfb_pool01.contoso.local 的範例。
    
   - 您應該輸入**/*** 時要發佈、 路徑，但您也需要**轉寄原始主機標頭**。
    
   - 會為**公用或外部名稱**詳細資料] 或 [資訊] 選項。 這是其中您可以輸入的位置：
    
   - **接受要求**，但它應該是網域名稱。
    
   - 對於**名稱**] 中，您應該輸入**lyncdiscover。** <sipdomain>（這是外部自動探索服務 URL）。 現在，如果您正在建立規則的前端集區上的外部 Web 服務 URL，您需要輸入您的前端集區 (例如 lyncwebextpool01.contoso.com) 上的外部 Web 服務 FQDN。
    
   - 將**路徑**] 選項，而您將需要輸入**/*** 以下。
    
   - 您需要選取與您最新的公用憑證的**SSL 接聽程式**。
    
   - **驗證委派**應該設定為 [**沒有委派**，但直接用戶端驗證**應**被允許。
    
   - 在規則應設定為**所有使用者**。
    
   - 這應該是您要建立此規則，並可讓您可繼續進行的所有資訊。
    
4. 您要需要確保會轉寄**原始主機標頭**。
    
5. **Web 伺服器**連接埠必須也要設定，您需要執行下列動作：
    
   - **重新導向至 HTTP 連接埠的要求**和連接埠號碼應該**8080**。
    
   - **重新導向至 SSL 連接埠的要求**和連接埠號碼應該**4443**。
    
6. 設定每個項目時，您需要儲存或套用這些項目，，然後您會想要測試規則。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>建立網頁發行規則的連接埠 80 （選用）

1. 開啟您的反向 proxy 介面。
    
2. 您需要找出其中介面中您建立網頁發行規則，並選擇 [**新增**] 或 [**建立**] 選項 （可能為功能表或根據您的反向 proxy 設定] 索引標籤）。 您要尋找要建立新的 web 發行規則的選項。
    
3. 一般而言，您需要輸入下列資訊：
    
   - **名稱**： 您的規則的名稱
    
   - **規則動作**： 在此情況下是**允許**規則，就會讓通過反向 proxy 的某個項目。
    
   - 您選擇的**發佈**規則或選項就是**單一網站或負載平衡器**。
    
   - 這必須是**非安全連線來連線到發行的 Web 伺服器或伺服器陣列**。
    
   - 您將需要發佈**內部發佈**，路徑，並輸入 FQDN，前端集區的負載平衡器的**VIP 位址**，範例會為 sfb_pool01.contoso.local。
    
   - 您應該輸入**/*** 時要發佈、 路徑，但您也需要**轉寄原始主機標頭**。
    
   - 會為**公用或外部名稱**詳細資料] 或 [資訊] 選項。 這是其中您可以輸入的位置：
    
   - **接受要求**，但它應該是網域名稱。
    
   - 對於**名稱**] 中，您應該輸入**lyncdiscover。** <sipdomain>（這是外部自動探索服務 URL）。
    
   - 將**路徑**] 選項，而您將需要輸入**/*** 以下。
    
   - 您需要選取網頁接聽程式，或可讓您建立另一個適用於您的反向 proxy。
    
   - **驗證委派**應該設定為 [**沒有委派**，但直接用戶端驗證**不應**被允許。
    
   - 在規則應設定為**所有使用者**。
    
   - 這應該是您要建立此規則，並可讓您可繼續進行的所有資訊。
    
4. **Web 伺服器**連接埠必須要設定，您需要執行下列動作：
    
   - **重新導向至 HTTP 連接埠的要求**和連接埠號碼應該**8080**。
    
   - **重新導向至 SSL 連接埠的要求**和連接埠號碼應該**4443**。
    
5. 設定每個項目時，您需要儲存或套用這些項目，，然後您會想要測試規則。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>使用混合式部署設定行動的自動探索
<a name="ConfigAutoD"> </a>

Skype for Business Server 的混合式環境是結合內部部署的環境和 O365 環境。 當您有 Skype for Business Server 混合式環境中工作時，自動探索服務必須能夠找到其中一個這些環境中的使用者。
  
若要讓行動用戶端探索使用者所在的位置，自動探索服務必須設定與新的統一資源定位器 (URL)。 步驟如下：
  
1. 開啟 Skype for Business Server 管理命令介面。
    
2. 執行下列命令以取得您 Skype for Business Server 環境屬性**ProxyFQDN**的值：
    
   ```powershell
   Get-CsHostingProvider
   ```

3. 然後，仍在命令介面] 視窗中，執行：
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    其中 [identity] 被取代共用 SIP 位址空間的網域名稱。
    
## <a name="test-your-mobility-deployment"></a>測試行動性部署
<a name="TestMobility"> </a>

一旦您已部署 Business Server Mobility Service 和 Skype 的 Skype for Business Server 自動探索服務，您會想要執行測試的交易時，若要確保您的部署工作右邊。 您可以執行**Test-csucwaconference**若要測試的兩個使用者建立、 加入及會議中進行通訊的能力。 您將需要兩位使用者 （實數或測試） 和其完整認證來執行這項操作測試。 此命令將這兩個 skype 適合商務用戶端，以及 Lync Server 2013 用戶端。
  
對於商務用 Skype Server 2015 上的 Lync Server 2010 用戶端，您需要執行**Test-csmcxp2pim**來測試。 您的 Lync Server 2010 使用者仍必須為實際使用者或預先定義的測試使用者，而您將需要其密碼的認證。

> [!NOTE]
> MCX (Mobility Service) 支援舊版的行動用戶端已不再提供 skype for Business Server 2019。 所有目前的 Skype for Business 行動用戶端已使用 Unified Communications Web API (UCWA) 來支援立即訊息 (IM)、 目前狀態和連絡人。 使用舊版用戶端使用 MCX 使用者必須升級至目前的用戶端。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>測試會議 skype for Business 和 Lync 2013 行動用戶端

1. 在任一安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦上**CsAdministrator**角色的成員身分登入。
    
2. 啟動**Skype for Business Server 管理命令介面**（您可能在搜尋中輸入名稱或移到 [**所有程式]** 然後選擇 [它）。
    
3. 在命令列，請輸入：
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   它也可在指令碼中設定認證，並將其傳遞至 test cmdlet。 我們有下列的範例。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>測試 Lync 2010 行動用戶端的會議

> [!NOTE]
> MCX (Mobility Service) 支援舊版的行動用戶端已不再提供 skype for Business Server 2019。 所有目前的 Skype for Business 行動用戶端已使用 Unified Communications Web API (UCWA) 來支援立即訊息 (IM)、 目前狀態和連絡人。 使用舊版用戶端使用 MCX 使用者必須升級至目前的用戶端。

1. 在任一安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦上**CsAdministrator**角色的成員身分登入。
    
2. 啟動**Skype for Business Server 管理命令介面**（您可能在搜尋中輸入名稱或移到 [**所有程式]** 然後選擇 [它）。
    
3. 在命令列，請輸入：
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   它也可在指令碼中設定認證，並將其傳遞至 test cmdlet。 我們有下列的範例。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

若要檢閱的命令程序此外，您可以查看[Test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)和[Test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>設定推入通知
<a name="ConfigPush"> </a>

推入通知，形式的徽章、 圖示或提醒，可以傳送至行動裝置，即使 Skype 或 Lync 應用程式是不在作用中。 但什麼是推入通知？ 它們是事件通知，例如新的或未接的 IM 邀請，或收到的語音信箱。 Skype for Business Server Mobility service 將這些通知傳送至雲端式用 Skype 的商務伺服器推播通知服務，然後將傳送通知到 Microsoft 推播通知服務 (MSNS) for Windows Phone 的使用者。
  
這項功能是從 Lync Server 2013 中，不變，但如果您有 Skype for Business Server 時，您會想要執行下列動作：
  
- Skype for Business Server Edge Server，新增新主機服務提供者，Microsoft Skype for Business Online，然後再設定裝載提供者同盟之間您的組織與 Skype for Business Online。
    
- 執行**Set-cspushnotificationconfiguration** cmdlet 來啟用推入通知。 根據預設，推入通知被關閉的。
    
- 測試同盟設定和推入通知。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>設定您 Skype for Business Edge Server 推入通知

1. 是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。
    
2. 啟動**Skype for Business Server 管理命令介面**。
    
3. 新增 Skype for Business Server 線上裝載提供者。
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   做為範例：
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 您不能有一個以上的同盟關係與單一主機服務提供者。 因此，如果您已經設定好裝載提供者已與 sipfed.online.lync.com 的同盟關係，不新增另一台主機服務提供者，即使裝載提供者的身分識別是 SkypeOnline 以外的項目。 
  
4. 設定裝載提供者同盟之間您的組織和推入通知服務在 Skype for Business Online。 在命令列，您需要輸入：
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>啟用推入通知

1. 是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。
    
2. 啟動**Skype for Business Server 管理命令介面**。
    
3. 啟用推播通知：
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 啟用同盟：
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>測試同盟和推入通知

1. 是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。
    
2. 啟動**Skype for Business Server 管理命令介面**。
    
3. 測試同盟設定：
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    做為範例：
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. 測試推入通知：
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    做為範例：
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>設定行動性原則
<a name="ConfigMob"> </a>

您可以與 Skype for Business 伺服器，以判定誰可以使用您的行動性服務，呼叫從公司，voice over IP (VoIP) 或視訊，以及是否 WiFi 將會需要 VoIP 或視訊。 從公司撥號可讓行動裝置使用者使用其公司電話號碼，而不是其行動電話號碼，撥打和接聽電話時。 在 [其他線條結尾的人員不會看到該行動使用者的行動電話號碼，以及它可讓行動使用者避免撥出通話費。 當 VoIP 和視訊設定時，使用者可以採取，並讓 VoIP 通話和視訊。 WiFi 流量的設定會決定使用者的行動裝置是否必須透過行動數據網路使用 WiFi 網路。
  
行動性、 工作，透過呼叫和 VoIP 和視訊功能會啟用所有預設值。 需要 VoIP 和視訊 WiFi 設定會停用。 系統管理員必須能夠變更此設定，全域、 網站，或藉由使用者。
  
若要能夠使用行動功能和呼叫從公司，使用者必須為：
  
- 啟用 skype for Business Server
    
- 啟用企業語音。
    
- 指派 [ **enablemobility]** 選項設為**True**的行動性原則。
    
為了能夠使用從公司撥號的使用者，他們也需要為：
  
- 指派語音原則已選取 [**啟用同時電話響鈴**] 選項。
    
- 指派 [ **EnableOutsideVoice**設為**True**的行動性原則。
    
> [!NOTE]
> 未啟用 Enterprise Voice 的使用者可以使用其行動裝置 Skype 對 Skype VoIP 通話或可以在其行動裝置上使用 [按一下以加入連結時加入會議時，如果語音原則設定的適當選項它們關聯使用。 規劃主題中沒有更多詳細資料。 
  
### <a name="modify-global-mobility-policy"></a>修改全域行動性原則

1. 是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。
    
2. 啟動**Skype for Business Server 管理命令介面**。
    
3. 關閉對存取 Mobility] 和 [從公司撥號全域輸入：
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 您可以關閉從公司撥號，而不必關閉行動存取。 但您無法關閉行動性而不必也關閉從公司撥號。 
  
    如需詳細資訊，請參閱[Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>依網站修改行動原則

1. 是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。
    
2. 啟動**Skype for Business Server 管理命令介面**。
    
3. 您可以建立網站層級原則、 關閉 VoIP 和視訊、 啟用 IP 音訊需要 WiFi 和需要 WiFi 如 IP 視訊由站台。 類型：
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    深入瞭解[New-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-user"></a>依使用者修改行動原則

1. 是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。
    
2. 啟動**Skype for Business Server 管理命令介面**。
    
3. 建立使用者層級的行動性原則，並關閉行動性和呼叫從使用者的公司。 類型：
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    將含有範例資料進一步範例：
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > 您可以關閉從公司撥號，而不必關閉行動存取。 但您無法關閉行動性而不必也關閉從公司撥號。 
  

