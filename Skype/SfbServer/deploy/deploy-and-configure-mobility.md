---
title: 部署及設定商務用 Skype Server 的行動性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文將逐步逐步指導您設定現有的商務用 Skype Server 安裝以使用行動裝置服務，讓行動裝置能夠利用商務用 Skype Server 行動功能。
ms.openlocfilehash: 4e2cbb49d74347082bf3db02bba4a01de7f31ca187867b8e95474e88ec01fcbb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306035"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>部署及設定商務用 Skype Server 的行動性  
 
本文將逐步逐步指導您設定現有的商務用 Skype Server 安裝以使用行動裝置服務，讓行動裝置能夠利用商務用 Skype Server 行動功能。
  
已複習[商務用 Skype Server 文章行動方案的計畫](../plan-your-deployment/mobility.md)，您應該準備好繼續執行下列步驟，以將行動性部署至您的商務用 Skype Server 環境。 步驟如下 (，我們會在此表格中包含許可權清單) ：
  
|**階段**|**權限**|
|:-----|:-----|
|[建立 DNS 記錄](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[修改憑證](deploy-and-configure-mobility.md#ModCerts) <br/> |本機系統管理員  <br/> |
|[設定反向 Proxy](deploy-and-configure-mobility.md#ConfigRP) <br/> |本機系統管理員  <br/> |
|[設定具有混合式部署行動的自動探索](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[測試行動性部署](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[設定推入通知](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[設定行動性原則](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
下列各節包含假設您已閱讀規劃主題的步驟。 如果有任何混淆，請隨意查看資訊。

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
## <a name="create-dns-records"></a>建立 DNS 記錄
<a name="CreateDNSRec"> </a>

您可能已經將它們當做商務用 Skype Server 環境的一部分，但是您必須建立下列記錄，才能讓「自動探索」運作：
  
- 內部 DNS 記錄，以支援從組織網路內部連線的行動使用者。
    
- 外部 (或公開) DNS 記錄，以支援從組織網路外部連線的行動使用者。
    
這些記錄可以是 (主機) 名稱或 CNAME 記錄， (您不需要做這兩種，我們只會在這裡) 的所有步驟中包含步驟。
  
### <a name="create-an-internal-dns-cname-record"></a>建立內部 DNS CNAME 記錄

1. 登入您網路中的 DNS 伺服器，該伺服器是 **Domain Admins** 群組的成員，或是 **DnsAdmins** 群組的成員。
    
2. 按一下 [**開始**]，選擇 [系統 **管理工具**] (如果不是 [開始] 功能表) 的選項，請加以 **搜尋**，然後按一下 [ **dns** ] 以開啟 [dns 管理] 嵌入式管理單元。
    
3. 在主控台視窗的左窗格中，您必須前往商務用 Skype Server 前端伺服器的首頁，然後展開其中的 **正向對應區域**。
    
4. 請花一點時間來查看您有下列哪一項：
    
   - 前端伺服器的任何主機 A 或 AAAA 記錄 (Standard 或 Enterprise) 或前端集區 (s) 。
    
   - Director 或 Director 集區的任何主機 A 或 AAAA 記錄 (您在部署) 中的選用設定。
    
5. 在您記下之後，請以滑鼠右鍵按一下 SIP 功能變數名稱，然後從功能表中選取 [ **新增別名 (CNAME)** 。
    
6. 在 [ **別名名稱** ] 文字方塊中，輸入 lyncdiscoverinternal 的主機名稱，以供內部自動探索服務 URL。
    
7. 在 [ **目標主機的完整功能變數名稱 (FQDN**] 中，您必須輸入或流覽至前端集區的內部 WEB 服務 FQDN (或單一前端伺服器或 director) （在上述步驟4中識別）。 輸入時，按一下 [確定]。
    
8. 您必須在正向對應區域中，為商務用 Skype Server 環境所支援的每個 SIP 網域建立新的自動探索 CNAME 記錄。
    
### <a name="create-an-external-dns-cname-record"></a>建立外部 DNS CNAME 記錄

1. 這些步驟是一般的，因為我們無法判斷可能使用的公用 DNS 提供者，但我們仍想要協助您。請使用可讓新 DNS 記錄的帳戶登入您的公用 DNS 提供者。
    
2. 在此時間，SIP 網域應該已存在於商務用 Skype Server。 展開這個 SIP 網域的 **正向對應區域** ，或以其他方式開啟它。
    
3. 請花一點時間來查看您有下列哪一項：
    
   - 前端伺服器的任何主機 A 或 AAAA 記錄 (Standard 或 Enterprise) 或前端集區 (s) 。
    
   - Director 或 Director 集區的任何主機 A 或 AAAA 記錄 (您在部署) 中的選用設定。
    
4. 取得該資訊後，您就可以選取一個選項來建立 **新的別名 (CNAME)**。
    
5. 現在您應該可以輸入 **別名**，您必須在這裡為外部自動探索服務 URL 輸入 lyncdiscover。
    
6. 接下來應該是一個區域，可在 **目標主機的 fqdn** 內輸入，這必須是前端集區的 FQDN (或單一前端伺服器的 fqdn，或是 director 集區或 director) （在上述步驟3中識別）。
    
7. 您可能需要儲存在這裡，或者，如果您需要在商務用 Skype Server 環境中的每個 SIP 網域的正向對應區域中建立其他 CNAME 記錄，您應該這麼做，但在您準備好之後，請儲存您的工作。
    
### <a name="create-an-internal-dns-a-record"></a>建立內部 DNS A 記錄

1. 登入您網路中的 DNS 伺服器，該伺服器是 **Domain Admins** 群組的成員，或是 **DnsAdmins** 群組的成員。
    
2. 按一下 [**開始**]，選擇 [系統 **管理工具**] (如果不是 [開始] 功能表) 的選項，請加以 **搜尋**，然後按一下 [ **dns** ] 以開啟 [dns 管理] 嵌入式管理單元。
    
3. 在主控台視窗的左窗格中，您必須前往商務用 Skype Server 前端伺服器的首頁，然後展開其中的 **正向對應區域**。
    
4. 請花一點時間來查看您有下列哪一項：
    
   - 前端伺服器的任何主機 A 或 AAAA 記錄 (Standard 或 Enterprise) 或前端集區 (s) 。
    
   - Director 或 Director 集區的任何主機 A 或 AAAA 記錄 (您在部署) 中的選用設定。
    
5. 在您記下之後，請以滑鼠右鍵按一下 SIP 功能變數名稱，然後從功能表中選擇 [ **新增主機 (A 或 AAAA)** ]。
    
6. 在 [ **名稱** ] 文字方塊中，輸入 lyncdiscoverinternal 的主機名稱，以供內部自動探索服務 URL。
    
7. 在 [ **IP 位址** ] 文字方塊中，輸入前端集區的內部 WEB 服務 IP 位址 (或單一前端伺服器，或是 director 集區或 director) （在上述步驟4中識別）。
    
8. 完成後，按一下 [ **新增主機**]，然後按一下 **[確定]**。
    
9. 您需要為商務用 Skype Server 環境中支援的每個 SIP 網域，在正向對應區域中建立新的自動探索 a 或 AAAA 記錄。 若要這麼做，請視需要重複步驟6-8。
    
10. 當您完成時，請按一下 [ **完成**]。
    
### <a name="create-an-external-dns-a-record"></a>建立外部 DNS A 記錄

1. 這些步驟是一般的，因為我們無法判斷可能使用的公用 DNS 提供者，但我們仍想要協助您。請使用可讓新 DNS 記錄的帳戶登入您的公用 DNS 提供者。
    
2. 在此時間，SIP 網域應該已存在於商務用 Skype Server。 展開這個 SIP 網域的 **正向對應區域** ，或以其他方式開啟它。
    
3. 請花一點時間來查看您有下列哪一項：
    
   - 前端伺服器的任何主機 A 或 AAAA 記錄 (Standard 或 Enterprise) 或前端集區 (s) 。
    
   - Director 或 Director 集區的任何主機 A 或 AAAA 記錄 (您在部署) 中的選用設定。
    
4. 一旦您獲得資訊之後，您應該能夠選取選項來建立 **新的主機 a 或 AAAA**。
    
5. 現在您應該可以輸入 **名稱**，您必須在這裡為外部自動探索服務 URL 輸入 lyncdiscover。
    
6. 接下來，您應該要有一個區域可在 **IP Addresss** 中輸入，這必須是前端集區的 IP (或單一前端伺服器，或是 director 集區或 director) （在上述步驟3中所識別）。
    
7. 您可能需要儲存在這裡，或者，如果您需要在商務用 Skype Server 環境的每個 SIP 網域的正向對應區域中建立額外的 A 或 AAAA 記錄，您應該這麼做，但在您準備好之後，請儲存您的工作。
    
## <a name="modify-certificates"></a>修改憑證
<a name="ModCerts"> </a>

如果您有關于如何規劃憑證的相關問題，我們已在我們[為商務用 Skype Server 文章的行動方案](../plan-your-deployment/mobility.md)中記錄這方面的問題。 一旦您已複習好，我們會逐步引導您完成下列作業：
  
- 我是否需要新的憑證？
    
- 從憑證授權單位單位 (CA) 要求新憑證。
    
- 使用 PowerShell 來更新就地憑證和取代專案。
    
- 使用 Microsoft Management Console 中的憑證管理憑證檢查憑證 (MMC) 。
    
### <a name="do-i-need-new-certificates"></a>我是否需要新的憑證？

1. 首先，您可能需要檢查並查看存在哪些憑證，以及是否有您所需的專案。 若要這麼做，您必須使用本機系統管理員帳戶登入您的商務用 Skype Server。 此帳戶可能也需要 (CA) 的許可權，才能執行這些步驟中的部分。
    
2. 開啟商務用 Skype Server 管理命令介面 (當您未將其固定至 [開始] 功能表或工作列) 時，您可以使用「搜尋」來找出它。
    
3. 在您嘗試新增更新的憑證之前，您必須先知道哪些憑證已被指派，才是必要的做法。 因此，在命令中輸入：
    
   ```powershell
   Get-CsCertificate
   ```

4. 步驟3中的資訊將是您獨有的。 您必須查看此專案，以判斷您是否有多個專案指派的單一憑證，或是否已指派不同的憑證以供需要它們的不同元件使用。 **Use** 參數會告訴您憑證的使用方式，以及 **指紋** 參數會告訴您，是否全部都是相同的憑證或多個證書。
    
5. 如果您在規劃區段中有建議的 SAN 專案，您就會是好事。 如果不是，您必須要求新的憑證或多個憑證 (，視您的憑證授權單位) 設定而定。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>從憑證授權單位單位 (CA 要求新憑證或憑證) 

1. 檢查您所擁有的 SAN 專案後，您會知道您已透過) 上的步驟進行檢查後，您有 **一個憑證** (，而且您已學到您沒有所有需要的專案。 需要對您的 CA 進行新的憑證要求。 開啟商務用 Skype Server PowerShell:
    
   - 若缺少自動探索服務 SAN (將-Ca 參數取代為您自己的憑證授權單位路徑) ：
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 現在，如果您有多個 SIP 網域，您就無法使用 AllSipDomain 參數，如上述範例所示。 您必須改用 DomainName 參數。 當您使用 DomainName 參數時，您必須定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。 範例會 (以您自己的憑證授權單位單位路徑取代-Ca 參數) ：
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 或者，在您檢查您所擁有的 SAN 專案後，您就會發現有 **多個憑證** 沒有所有需要的專案。 需要對您的 CA 進行新的憑證要求。 開啟商務用 Skype Server PowerShell:
    
   - 若缺少自動探索服務 SAN (將-Ca 參數取代為您自己的憑證授權單位路徑) ：
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 現在，如果您有多個 SIP 網域，您就無法使用 AllSipDomain 參數，如上述範例所示。 您必須改用 DomainName 參數。 當您使用 DomainName 參數時，您必須定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。 範例會 (以您自己的憑證授權單位單位路徑取代-Ca 參數) ：
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - 一旦 CA 產生新的憑證後，您就必須將其指派給他們。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面指派憑證

- 您必須執行下列 **其中一** 項，視您在上述「我需要新的認證」一節中找到的專案而定。
    
  - 如果您擁有單一憑證 (指紋完全相同的憑證) 則需要執行下列動作：
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 如果您有不同的憑證 (指紋全都不同) ，請改為執行這項作業：
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>在 Microsoft Management Console 中查看憑證 (MMC) 

1. 您可以選擇使用 MMC 的憑證嵌入式管理單元來查看憑證。 只需在搜尋中輸入 MMC，它應會以應用程式選項形式彈出。
    
2. 若要新增憑證嵌入式管理單元，您 **必須按一下 [** 檔案]，然後按一下 [ **新增/移除嵌入式管理單元 ...** (] 或 [鍵盤 **快捷方式]** （) ）也可正常運作。 您可以在左側窗格中選擇 [**憑證**]，然後在快顯視窗中選取它，然後按一下 [**電腦帳戶**]，然後按一下 **[下一步**]。
    
3. 仍在快顯視窗中，在您所需查看的憑證所在的電腦上，只要您要執行此動作，否則請保留在 **本機電腦** 上的選取範圍。 如果您是在遠端電腦上運作，請將選項按鈕變更為 **另一部電腦** ，然後輸入該電腦的 FQDN，或使用 [ **流覽]** 按鈕，透過 AD 搜尋該電腦。 選取電腦之後，您需要在 [就緒時按一下 **[完成]** ，然後按一下 **[確定]** ，將嵌入式管理單元新增至 MMC。
    
4. 在 MMC 的左窗格中，展開 [ **憑證** ] 區段。 同時展開 [ **個人** ] 資料夾，然後選取 [ **憑證**]。 這可讓您查看此存放區中的憑證。
    
5. 您需要找出您想要查看的憑證，並在其上按一下滑鼠右鍵，然後選擇 [ **開啟**]。
    
    > [!NOTE]
    > 如何知道這是哪一個憑證？ 它應該是指派給伺服器陣列之所有專案的單一憑證，或者您可以針對不同的專案（如預設值、內部 Web 服務等）使用多個憑證，在這種情況下，您可能需要查看多個憑證。 多個憑證會有相同的指紋。 
  
6. 當您進入 **憑證** 視圖後，請選擇 [ **詳細資料**]。 這可讓您在選取 [主旨] 時查看憑證 **的主體** 名稱，並顯示指定的主體名稱和相關聯的屬性。
    
7. 您也需要檢查 **主體替代名稱** 專案。 您會發現下列一或多項：
    
   - 此集區的集區名稱，如果這不是集區，則為單一伺服器名稱。
    
   - 指派憑證的伺服器名稱。
    
   - 簡單 URL 記錄，通常是符合和撥入的。
    
   - Web 服務的內部及 Web 服務外部名稱 (例如，webpool01.contoso.net、webpool01.contoso.com) ，其依據拓撲產生器和透過 ridden Web 服務選取範圍內的選擇。
    
   - 如果已指派，則 lyncdiscover。\<sipdomain\> 和 lyncdiscoverinternal。\<sipdomain\> 記錄。
    
     如果您有一個以上指派的 (請檢查多個憑證。) 以上的附注。
    
8. 因此，如果您找到 lyncdiscover。\<sipdomain\> 和 lyncdiscoverinternal。\<sipdomain\> 您已設定此記錄。 您可以關閉 MMC。
    
9. 若未指派，您將需要 (以上所述的新憑證要求) 或您必須將其安裝後的要求 (我們建議針對該) 執行上述 PowerShell。
    
## <a name="configure-the-reverse-proxy"></a>設定反向 Proxy
<a name="ConfigRP"> </a>

下列步驟並不是完全遵循。 這是因為在舊版本的產品中，我們已引導您完成，例如設定威脅管理閘道 (TMG) ，但如果您沒有使用該功能，則必須從那裡使用您自己的版本。
  
TMG 不再是由 Microsoft 做為產品提供，如果您仍然需要加以設定，則可以查看 [Lync Server 2013 的步驟](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility)。 不過，下列資訊的目的應該更普遍有用，即使沒有任何方法可以提供每個反向 proxy 的特定逐步步驟。
  
我們有兩個主要考慮事項：
  
- 您是否要透過 HTTPS (執行初始自動探索要求，我們建議) ？
    
  - 如果您有 web 發佈規則，您必須加以修改。
    
  - 如果您還沒有網路發佈規則，則必須加以建立。
    
- 如果您是透過 HTTP 進行初始自動探索要求，您也必須建立或修改該規則。
    
> [!NOTE]
> **重要事項** Proxy 超時值是一個數位，會因部署而異。 您應該監視您的部署，並修改用戶端的最佳體驗值。 您可以將值設為低200。 如果您在環境中支援 Lync 行動用戶端，則應該將值設為960，以允許來自 Office 365 的推播通知超時，其超時值為900。 您很可能需要增加超時值，以避免用戶端在值太低時中斷連線，或在用戶端中斷連線後，如果經由 proxy 的連線不會中斷連線，則降低數目。 監視及設定環境的一般功能是判斷此值適當設定的唯一準確方式。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>為外部自動探索 SAN 和 URL 修改現有的 web 發行規則

1. 開啟反向 proxy 介面。
    
2. 您需要找出您的 web 發行規則，然後選擇 [編輯] 選項 (它可能位於功能表或索引標籤上，視您的反向 proxy 設定) 而定。
    
3. 應該會有一個區域，指出此 web 發行規則的套用目標。 您必須修改傳入網站或網站要求的此規則。 您即將 **加入** 新的專案。
    
4. 輸入自動探索網站的名稱 (我們將使用的範例是 lyncdiscover.contoso.com) ]，然後根據您的反向 proxy 格式，按一下 **[確定] 或 [** **儲存**]。
    
5. 您的新憑證可能具有「自動探索」 SAN 專案。 必須同時安裝和設定，以根據您的反向 proxy 設定進行使用。 設定完成時，請務必儲存所有專案。
    
6. 如果反向 proxy 具有 **測試** 功能，請使用它，以確保一切運作正常。
    
7. 現在，如果您在環境中有 Director 或 Director 集區，您可能需要重複這些步驟。 (這意味著您有第二個規則) 。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>建立外部自動探索 URL 的 web 發行規則

1. 開啟反向 proxy 介面。
    
2. 您需要找出在介面中建立 web 發行規則的位置，然後選擇 [ **新增** ] 或 [ **建立** ] 選項 (它可能位於功能表或索引標籤上，視您的反向 proxy 設定) 而定。 您正在尋找選項來建立新的 web 發行規則。
    
3. 一般來說，您必須輸入下列資訊：
    
   - **名稱**：規則的名稱
    
   - **規則動作**：在此情況下，它是一個 **允許** 規則，您可以透過您的反向 proxy 進行某項處理。
    
   - 您所選擇的 **發佈** 規則或選項，就是 **單一網站或負載平衡器**。
    
   - 這必須是 **SSL** 才能進行外部存取，請選擇該選項。
    
   - 您將需要發行 **內部發佈** 的路徑，然後在前端集區的負載平衡 (器上輸入外部 Web 服務的 fqdn，如果您有一個) ，就會 sfb_pool01 一個範例（如有一個）。
    
   - 您應輸入 **/\\** _ 作為要發佈的路徑，但您也需要將原始的主機標頭轉寄給您。
    
   - **公用或外部名稱** 詳細資料或資訊都有一個選項。 您可以在此位置輸入：
    
   - **接受要求**，但應為功能變數名稱。
    
   - 您應輸入 lyncdiscover 的 **名稱** **。** <sipdomain> (這是) 的外部自動探索服務 URL。 現在，如果您要為前端集區上的外部 Web 服務 URL 建立規則，您必須在前端集區上輸入外部 Web 服務的 FQDN (例如，lyncwebextpool01.contoso.com) 。
    
   - 會有一個 **路徑** 選項，您必須在 **/\\** 這裡輸入 *。
    
   - 您必須選取具有最新公開憑證的 **SSL 攔截器** 。
    
   - **驗證委派** 應設定為 [ **不委派**]，但 **應** 允許直接用戶端驗證。
    
   - 規則應設定為 [ **所有使用者**]。
    
   - 這應該是您建立此規則所需的所有資訊，並可讓您繼續。
    
4. 您必須確定 **原始的主機標頭** 已轉寄。
    
5. **網頁伺服器** 埠也必須設定，您必須執行下列動作：
    
   - 將 **要求重新導向至 HTTP 埠**，埠號碼應該是 **8080**。
    
   - 將 **要求重新導向至 SSL 埠**，埠號碼應該是 **4443**。
    
6. 設定好任何專案時，您必須儲存或套用這些專案，然後您將需要測試規則。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>建立埠80的 web 發行規則 (選用) 

1. 開啟反向 proxy 介面。
    
2. 您需要找出在介面中建立 web 發行規則的位置，然後選擇 [ **新增** ] 或 [ **建立** ] 選項 (它可能位於功能表或索引標籤上，視您的反向 proxy 設定) 而定。 您正在尋找選項來建立新的 web 發行規則。
    
3. 一般來說，您必須輸入下列資訊：
    
   - **名稱**：規則的名稱
    
   - **規則動作**：在此情況下，它是一個 **允許** 規則，您可以透過您的反向 proxy 進行某項處理。
    
   - 您所選擇的 **發佈** 規則或選項，就是 **單一網站或負載平衡器**。
    
   - 這必須是不安全的連線， **才能連線至發佈的網頁伺服器或伺服器** 陣列。
    
   - 您將需要發行 **內部發佈** 的路徑，並輸入前端集區之負載平衡器之 **VIP 位址** 的 FQDN，例如，sfb_pool01 為 contoso。
    
   - 您應輸入 **/\\** _ 作為要發佈的路徑，但您也需要將原始的主機標頭轉寄給您。
    
   - **公用或外部名稱** 詳細資料或資訊都有一個選項。 您可以在此位置輸入：
    
   - **接受要求**，但應為功能變數名稱。
    
   - 您應輸入 lyncdiscover 的 **名稱** **。** <sipdomain> (這是) 的外部自動探索服務 URL。
    
   - 會有一個 **路徑** 選項，您必須在 **/\\** 這裡輸入 *。
    
   - 您必須選取網頁接聽程式，或允許您的反向 proxy 為您建立一個攔截器。
    
   - **驗證委派** 應該設定為 [ **不委派**]，但 **不** 允許直接的用戶端驗證。
    
   - 規則應設定為 [ **所有使用者**]。
    
   - 這應該是您建立此規則所需的所有資訊，並可讓您繼續。
    
4. 需要設定 **網頁伺服器** 埠，您需要執行下列作業：
    
   - 將 **要求重新導向至 HTTP 埠**，埠號碼應該是 **8080**。
    
   - 將 **要求重新導向至 SSL 埠**，埠號碼應該是 **4443**。
    
5. 設定好任何專案時，您必須儲存或套用這些專案，然後您將需要測試規則。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>設定具有混合式部署行動的自動探索
<a name="ConfigAutoD"> </a>

商務用 Skype Server 中的混合式環境是結合內部部署和 O365 環境的環境。 當您在混合式環境中工作商務用 Skype Server 時，自動探索服務必須能夠從這些環境中尋找使用者。
  
若要讓行動用戶端探索使用者所在的位置，必須使用新的統一資源定位器 (URL) ，來設定自動探索服務。 步驟如下：
  
1. 開啟商務用 Skype Server 管理命令介面。
    
2. 執行下列動作，以取得商務用 Skype Server 環境的屬性 **ProxyFQDN** 值：
    
   ```powershell
   Get-CsHostingProvider
   ```

3. 然後，在命令介面視窗中，執行：
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    其中 [identity] 以共用 SIP 位址空間的功能變數名稱取代。
    
## <a name="test-your-mobility-deployment"></a>測試行動性部署
<a name="TestMobility"> </a>

當您部署商務用 Skype Server 行動性服務並商務用 Skype Server 自動探索服務之後，您會想要執行測試交易，以確定部署的運作許可權。 您可以執行 **Test-CsUcwaConference** ，以測試兩位使用者在會議中建立、加入和通訊的能力。 您需要有兩位使用者 (實際或測試) 及其完整認證，才能進行此項測試。 商務用 Skype 用戶端和 Lync Server 2013 用戶端都可以使用此命令。
  
針對商務用 Skype Server 2015 上的 Lync Server 2010 用戶端，您必須執行 **Test-CsMcxP2PIM** 以進行測試。 您的 Lync Server 2010 使用者仍必須是實際使用者或預先定義的測試使用者，而且您將需要其密碼認證。

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>測試會議的商務用 Skype 和 Lync 2013 行動用戶端

1. 在安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的任何電腦上，以 **CsAdministrator** 角色成員的身分登入。
    
2. 啟動 **商務用 Skype Server 管理命令** 介面 (您可以在 [搜尋] 中輸入名稱，或是移至 [**所有程式**] 並選擇) 。
    
3. 在命令列中輸入：
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   您也可以在腳本中設定認證，並將認證傳遞至 test Cmdlet。 我們有下列範例。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>測試 Lync 2010 行動用戶端的會議

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。

1. 在安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的任何電腦上，以 **CsAdministrator** 角色成員的身分登入。
    
2. 啟動 **商務用 Skype Server 管理命令** 介面 (您可以在 [搜尋] 中輸入名稱，或是移至 [**所有程式**] 並選擇) 。
    
3. 在命令列中輸入：
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   您也可以在腳本中設定認證，並將認證傳遞至 test Cmdlet。 我們有下列範例。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

若要進一步複查命令過程，您可以取出 [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) 和 [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>設定推入通知
<a name="ConfigPush"> </a>

即使 Skype 或 Lync 應用程式非使用中，也可以將「徽章」、圖示或警示等推播通知傳送給行動裝置。 但什麼是推播通知？ 它們是事件警示，例如新的或錯過的 IM 邀請，或是收到的語音信箱。 商務用 Skype Server 行動性服務會將這些通知傳送至雲端式商務用 Skype Server 推播通知服務，然後將通知傳送至 Microsoft 推播通知服務 (MSNS) ，以供 Windows Phone 使用者。
  
這項功能在 Lync Server 2013 中是不變的，但是如果您有商務用 Skype Server，您會想要執行下列作業：
  
- 若為商務用 Skype Server Edge Server，請新增新的主機服務提供者、Microsoft 商務用 Skype 線上，然後設定組織和商務用 Skype Online 之間的裝載提供者同盟。
    
- 執行 **Set-CsPushNotificationConfiguration** Cmdlet 以啟用推播通知。 依預設，推播通知會關閉。
    
- 測試同盟設定及推播通知。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>設定推播通知的商務用 Skype Edge Server

1. 使用 **CsAdministrator** 角色成員的帳戶登入，以安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。
    
2. 啟動 **商務用 Skype Server 管理命令** 介面。
    
3. 新增商務用 Skype Server online 主機服務提供者。
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   範例：
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 您不可以有多個與單一主機服務提供者的同盟關聯。 因此，如果您已設定與 sipfed.online.lync.com 具有同盟關聯的裝載提供者，請勿為其新增其他主機服務提供者，即使主機服務的身分識別是 SkypeOnline 以外的其他專案。 
  
4. 在商務用 Skype Online 設定組織與推播通知服務之間的主機服務同盟同盟。 您必須在命令列上輸入：
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>啟用推播通知

1. 使用 **CsAdministrator** 角色成員的帳戶登入，以安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。
    
2. 啟動 **商務用 Skype Server 管理命令** 介面。
    
3. 啟用推播通知：
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 啟用同盟：
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>測試同盟及推播通知

1. 使用 **CsAdministrator** 角色成員的帳戶登入，以安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。
    
2. 啟動 **商務用 Skype Server 管理命令** 介面。
    
3. 測試同盟設定：
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    範例：
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. 測試推播通知：
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    範例：
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>設定行動性原則
<a name="ConfigMob"> </a>

您可以使用商務用 Skype Server 來判斷誰可以使用您的行動服務、通話方式、透過 IP 語音 (VoIP) 或影片，以及 WiFi 或影片是否需要 VoIP。 「透過公司通話」可讓行動使用者在撥打和接聽電話時使用其公司電話號碼，而不是其行動電話號碼。 該行另一端的人員不會看到行動使用者的蜂窩電話號碼，並可讓行動使用者避免撥出的電話費用。 當您設定 VoIP 和影片時，使用者可以採取或撥打 VoIP 通話和影片。 [WiFi 使用狀況] 設定會決定使用者的行動裝置是否需要透過行動電話資料網路使用 WiFi 網路。
  
行動性、呼叫方式，以及 VoIP 和影片功能預設為啟用。 需要停用 WiFi VoIP 和影片的設定。 系統管理員可以變更全域、依網站，或由使用者變更此功能。
  
若要能夠透過工作使用行動功能及通話，使用者必須：
  
- 已啟用商務用 Skype Server
    
- 為企業語音啟用。
    
- 指派 **EnableMobility** 選項設定為 **True** 的行動原則。
    
若要讓使用者能夠使用「從公司撥號」，他們也必須：
  
- 已指定已選取 [ **啟用同時振鈴電話** ] 選項的語音原則。
    
- 指派 **EnableOutsideVoice** 設定為 **True** 的行動性原則。
    
> [!NOTE]
> 未啟用企業語音的使用者可以使用行動裝置，在行動裝置上使用 [按一下以加入] 連結，讓 Skype Skype VoIP 通話，也可以加入會議，如果為其相關聯的語音原則設定了適當的選項。 規劃主題中有更多詳細資料。 
  
### <a name="modify-global-mobility-policy"></a>修改全域行動性原則

1. 使用 **CsAdministrator** 角色成員的帳戶登入，以安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。
    
2. 啟動 **商務用 Skype Server 管理命令** 介面。
    
3. 透過輸入下列專案，關閉行動及透過工作撥打的電話：
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 您可以在不關閉行動存取的情況下，關閉工作的來電。 不過，您不能關閉行動性，也不會關閉「從公司通話」。 
  
    如需詳細資訊，請參閱 [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>依網站修改行動性原則

1. 使用 **CsAdministrator** 角色成員的帳戶登入，以安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。
    
2. 啟動 **商務用 Skype Server 管理命令** 介面。
    
3. 您可以建立網站層級原則、關閉 VoIP 和影片、啟用 IP 音訊的「需要」 WiFi，以及要求透過網站 WiFi 的 IP 影片。 類型：
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    若要深入瞭解，請參閱 [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-user"></a>依使用者修改行動性原則

1. 使用 **CsAdministrator** 角色成員的帳戶登入，以安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。
    
2. 啟動 **商務用 Skype Server 管理命令** 介面。
    
3. 建立使用者層級的行動性原則，關閉行動能力，並依使用者進行呼叫。 類型：
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    範例資料的進一步範例：
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > 您可以在不關閉行動存取的情況下，關閉工作的來電。 不過，您不能關閉行動性，也不會關閉「從公司通話」。 
