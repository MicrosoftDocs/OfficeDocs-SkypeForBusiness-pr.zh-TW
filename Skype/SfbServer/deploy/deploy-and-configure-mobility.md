---
title: 在商務用 Skype Server 上部署及設定行動性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文將逐步引導您設定現有的商務用 Skype Server 安裝, 以使用行動裝置服務, 讓您的行動裝置能夠利用商務用 Skype Server 行動裝置功能。
ms.openlocfilehash: 910e23e8aec18d36c3a7e4bda9e97828fb498802
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234572"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>在商務用 Skype Server 上部署及設定行動性  
 
本文將逐步引導您設定現有的商務用 Skype Server 安裝, 以使用行動裝置服務, 讓您的行動裝置能夠利用商務用 Skype Server 行動裝置功能。
  
在已複習[商務用 Skype server 文章的行動方案規劃](../plan-your-deployment/mobility.md)中, 您應該準備好繼續執行下列步驟, 將行動部署到您的商務用 skype Server 環境。 這些步驟如下所示 (這個表格中包含許可權清單):
  
|**分**|**許可權**|
|:-----|:-----|
|[建立 DNS 記錄](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |網域管理員  <br/> DNSAdmins  <br/> |
|[修改憑證](deploy-and-configure-mobility.md#ModCerts) <br/> |本機系統管理員  <br/> |
|[設定反向 proxy](deploy-and-configure-mobility.md#ConfigRP) <br/> |本機系統管理員  <br/> |
|[使用混合式部署設定自動探索以進行行動](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |網域管理員  <br/> |
|[測試行動部署](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[針對推播通知進行設定](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[設定行動原則](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
下列各節包含的步驟假設您已閱讀規劃主題。 如果有任何專案感到困惑, 請隨意查看其中的資訊。

> [!NOTE]
> MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
## <a name="create-dns-records"></a>建立 DNS 記錄
<a name="CreateDNSRec"> </a>

您可能已經將這些元件儲存在商務用 Skype Server 環境中, 但您必須建立下列記錄, 才能讓「自動完成」工作:
  
- 內部 DNS 記錄可支援從貴組織的網路內部連線的行動使用者。
    
- 外部 (或公用) DNS 記錄, 以支援從組織網路外部連線的行動使用者。
    
這些記錄可以是 (主機) 名稱或 CNAME 記錄 (您不需要同時進行), 我們只會在這裡加入所有專案的步驟。
  
### <a name="create-an-internal-dns-cname-record"></a>建立內部 DNS CNAME 記錄

1. 登入您網路中擁有**Domain Admins**群組或**DnsAdmins**群組成員的 DNS 伺服器。
    
2. 按一下 [**開始**], 選擇 [**管理工具**] (如果不是 [開始] 功能表中的選項, 您可能需要進行**搜尋**), 然後按一下 [ **dns** ] 以開啟 [dns 管理] 管理單元。
    
3. 在主控台視窗的左窗格中, 您需要移至商務用 Skype Server 前端伺服器所在的網域, 然後展開其中的**正向查閱區域**。
    
4. 請花點時間來查看下列哪一項:
    
   - 前端伺服器的任何主機 A 或 AAAA 記錄 (標準或企業) 或頂層端池 (s)。
    
   - 主管或主管池的任何主機 A 或 AAAA 記錄 (您在部署中可能會有的選用配置)。
    
5. 一旦您記下這個名稱, 請以滑鼠右鍵按一下您的 SIP 功能變數名稱, 然後從功能表選擇 [**新增別名 (CNAME)** ]。
    
6. 在 [**別名名稱**] 文字方塊中, 輸入您的主機名稱 lyncdiscoverinternal, 以取得內部自動探索服務 URL。
    
7. 在**完整的功能變數名稱 (目標主機的 FQDN**) 中, 您必須輸入或流覽至您的前臺主機池 (或單一前端伺服器, 或主管池或控制器) 的內部 WEB 服務 FQDN (在上述步驟4中發現)。 輸入時, 按一下 [確定]。
    
8. 您必須在 [轉寄查閱區域] 中針對商務用 Skype Server 環境中支援的每個 SIP 網域, 建立新的自動探索 CNAME 記錄。
    
### <a name="create-an-external-dns-cname-record"></a>建立外部 DNS CNAME 記錄

1. 這些步驟是一般的, 因為我們無法判斷您可能正在使用哪個公用 DNS 提供者, 但我們仍想協助您解決。請登入您的公用 DNS 提供者, 並將能夠在該處建立新的 DNS 記錄的帳戶。
    
2. 在這個時間點, 商務用 Skype Server 應該已經存在一個 SIP 網域。 展開此 SIP 網域的**正向查閱區域**, 或以其他方式開啟它。
    
3. 請花點時間來查看下列哪一項:
    
   - 前端伺服器的任何主機 A 或 AAAA 記錄 (標準或企業) 或頂層端池 (s)。
    
   - 主管或主管池的任何主機 A 或 AAAA 記錄 (您在部署中可能會有的選用配置)。
    
4. 取得該資訊之後, 您就應該能夠選取建立**新別名 (CNAME)** 的選項。
    
5. 現在, 您應該可以輸入**別名**, 您必須在這裡輸入 lyncdiscover, 以取得外部自動探索服務 URL。
    
6. 接下來, 應該有一個區域可在**目標主機的 FQDN**中輸入, 這將必須是您的前端池 (或單一前端伺服器, 或主管池或控制器) 的 fqdn (在上述步驟3中發現)。
    
7. 您可能需要儲存在這裡, 或者, 如果您需要在商務用 Skype Server 環境中的每個 SIP 網域的轉寄查閱區域中建立其他 CNAME 記錄, 您應該這樣做, 但準備好後, 請儲存您的工作。
    
### <a name="create-an-internal-dns-a-record"></a>建立內部 DNS A 記錄

1. 登入您網路中擁有**Domain Admins**群組或**DnsAdmins**群組成員的 DNS 伺服器。
    
2. 按一下 [**開始**], 選擇 [**管理工具**] (如果不是 [開始] 功能表中的選項, 您可能需要進行**搜尋**), 然後按一下 [ **dns** ] 以開啟 [dns 管理] 管理單元。
    
3. 在主控台視窗的左窗格中, 您需要移至商務用 Skype Server 前端伺服器所在的網域, 然後展開其中的**正向查閱區域**。
    
4. 請花點時間來查看下列哪一項:
    
   - 前端伺服器的任何主機 A 或 AAAA 記錄 (標準或企業) 或頂層端池 (s)。
    
   - 主管或主管池的任何主機 A 或 AAAA 記錄 (您在部署中可能會有的選用配置)。
    
5. 一旦您記下這個名稱, 請以滑鼠右鍵按一下您的 SIP 功能變數名稱, 然後從功能表選擇 [**新增主機 (A 或 AAAA)** ]。
    
6. 在 [**名稱**] 文字方塊中, 為您的主機名稱輸入 lyncdiscoverinternal, 以取得內部自動探索服務 URL。
    
7. 在 [ **IP 位址**] 文字方塊中, 輸入您的 [前端] 池 (或 [單一前端伺服器] 或 [控制器池]) 的內部 WEB 服務 IP 位址 (在上述步驟4中標出)。
    
8. 完成後, 請按一下 [**新增主機**], 然後按一下 **[確定]**。
    
9. 您需要針對商務用 Skype Server 環境中支援的每個 SIP 域, 在轉寄查閱區域中建立新的自動探索 A 或 AAAA 記錄。 若要這麼做, 請視需要重複步驟6-8。
    
10. 完成後, 請按一下 [**完成**]。
    
### <a name="create-an-external-dns-a-record"></a>建立外部 DNS A 記錄

1. 這些步驟是一般的, 因為我們無法判斷您可能正在使用哪個公用 DNS 提供者, 但我們仍想協助您解決。請登入您的公用 DNS 提供者, 並將能夠在該處建立新的 DNS 記錄的帳戶。
    
2. 在這個時間點, 商務用 Skype Server 應該已經存在一個 SIP 網域。 展開此 SIP 網域的**正向查閱區域**, 或以其他方式開啟它。
    
3. 請花點時間來查看下列哪一項:
    
   - 前端伺服器的任何主機 A 或 AAAA 記錄 (標準或企業) 或頂層端池 (s)。
    
   - 主管或主管池的任何主機 A 或 AAAA 記錄 (您在部署中可能會有的選用配置)。
    
4. 取得該資訊之後, 您就應該能夠選取建立**新主機 a 或 AAAA**的選項。
    
5. 現在, 您應該可以輸入**名稱**, 您必須在這裡輸入 lyncdiscover, 以取得外部自動探索服務 URL。
    
6. 接下來, 您必須在**Ip Addresss**中輸入一個區域, 才能在上述步驟3中找到您的前端池 (或單一前端伺服器, 或主管池或控制器) 的 IP。
    
7. 您可能需要儲存在這裡, 或者, 如果您需要在每個 SIP 網域的轉寄查閱區域中, 為您的商務用 Skype Server 環境建立額外的 A 或 AAAA 記錄, 您應該這樣做, 但在您準備好後, 儲存您的工作。
    
## <a name="modify-certificates"></a>修改憑證
<a name="ModCerts"> </a>

如果您有關于證書規劃的問題, 我們已在[針對商務用 Skype Server 文章的行動方案](../plan-your-deployment/mobility.md)中記錄這些問題。 審查完畢之後, 我們會逐步引導您完成下列作業:
  
- 我需要新的憑證嗎？
    
- 從您的憑證授權單位 (CA) 要求新的憑證。
    
- 使用 PowerShell 的替換更新您的就地憑證。
    
- 使用 Microsoft 管理主控台 (MMC) 中的 [憑證] 管理單元檢查憑證。
    
### <a name="do-i-need-new-certificates"></a>我需要新的憑證嗎？

1. 首先, 您可能需要檢查並查看有哪些憑證, 以及他們是否擁有您所需的專案。 若要這樣做, 您必須使用本機系統管理員帳戶登入商務用 Skype 伺服器。 此帳戶也可能需要擁有頒發憑證授權單位 (CA) 的許可權, 才能執行這些步驟。
    
2. 開啟商務用 Skype Server 管理命令介面 (如果您沒有將它釘選到 [開始] 功能表或工作列), 您可以使用 [搜尋] 來尋找它。
    
3. 在您嘗試新增已更新的憑證之前, 您必須先瞭解已指派的憑證才是必要的。 在命令中, 輸入:
    
   ```
   Get-CsCertificate
   ```

4. 步驟3中的資訊將對您而言是唯一的。 您需要查看它, 以判斷您是否有已指派給多個專案的單一憑證, 或是否有指派給其他需要不同元件的憑證。 **Use**參數會告知您證書的使用方式, 而**指紋**參數會告知您是否為相同的憑證或多個證書。
    
5. 如果您在 [規劃] 區段中有建議的 SAN 專案, 您就大功告成了。 如果不是, 您必須從您的憑證頒發機構要求新的憑證或多個憑證 (視您的設定而定)。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>從您的憑證頒發機構 (CA) 要求新憑證或憑證

1. 在您檢查並查看您擁有哪些 SAN 專案之後, 您會知道您有**單一憑證**(透過上述步驟檢查之後), 而且您已學到您沒有所有所需的專案。 需要對您的 CA 進行新的憑證要求。 開啟您的商務用 Skype Server PowerShell:
    
   - 針對遺失的自動探索服務 SAN (將-Ca 參數取代為您自己的憑證授權單位路徑):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 現在, 如果您有多個 SIP 網域, 就無法使用 AllSipDomain 參數, 如上述範例所示。 您必須改為使用 DomainName 參數。 當您使用 DomainName 參數時, 您必須為 lyncdiscoverinternal 和 lyncdiscover 記錄定義 FQDN。 例如, 將-Ca 參數取代為您自己的憑證授權單位路徑):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 或者, 在您檢查並查看您擁有哪些 SAN 專案之後, 您發現您有**多個憑證**沒有您所需的所有專案。 需要對您的 CA 進行新的憑證要求。 開啟您的商務用 Skype Server PowerShell:
    
   - 針對遺失的自動探索服務 SAN (將-Ca 參數取代為您自己的憑證授權單位路徑):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 現在, 如果您有多個 SIP 網域, 就無法使用 AllSipDomain 參數, 如上述範例所示。 您必須改為使用 DomainName 參數。 當您使用 DomainName 參數時, 您必須為 lyncdiscoverinternal 和 lyncdiscover 記錄定義 FQDN。 範例就是 (將-Ca 參數取代為您自己的憑證授權單位路徑):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - 一旦 CA 產生新憑證之後, 您就必須指派給他們。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management 命令介面指派憑證

- 您必須執行下列**其中一**項, 才能視您在上述 [我需要新認證] 區段中找到的內容而定。
    
  - 如果您的所有專案都有單一憑證 (指紋完全相同), 則必須執行以下動作:
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 如果您有不同的憑證 (指紋全都不一樣), 請改為執行此動作:
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>在 Microsoft 管理主控台 (MMC) 中查看憑證

1. 您可以選擇使用 MMC 的 [憑證] 管理單元來查看您的憑證。 只要在搜尋中輸入 MMC, 就應該將它作為應用程式選項彈出。
    
2. 若要新增 [憑證] 管理單元, 您需要按一下 [ **** 檔案], 然後按一下 [**新增/移除管理單元 ...** ]。(或鍵盤快速鍵**Ctrl + M**也會起作用)。 [**憑證**] 是左窗格中的一個選項, 選取它, 然後在快捷視窗中選取 [**電腦帳戶**], 然後按一下 **[下一步**]。
    
3. 在快顯視窗中, 您的所有可能性都是在您需要查看之憑證的電腦上執行此動作, 所以請在**本機電腦**上保留選取狀態 (如果有的話)。 如果您是在遠端電腦上工作, 請將選項按鈕變更為**另一部電腦**, 然後輸入該電腦的 FQDN, 或使用 **[流覽]** 按鈕, 透過廣告搜尋該電腦。 選取電腦之後, 您必須在 [就緒] 後按一下 **[完成]** , 然後按一下 **[確定]** , 將該管理單元新增至 MMC。
    
4. 展開 MMC 左側窗格中的 [**憑證**] 區段。 同時展開 [**個人**] 資料夾, 然後選取 [**憑證**]。 這可讓您查看此存放區中的憑證。
    
5. 您必須找出您想要查看的憑證, 然後以滑鼠右鍵按一下它, 然後選擇 [**開啟**]。
    
    > [!NOTE]
    > 如何知道這是哪一種證書？ 它應該是指派給您伺服器陣列所有專案的單一憑證, 或者您可能會有多個憑證的不同專案 (例如預設、內部 Web 服務等)。在這種情況下, 您可能需要查看多個憑證。 多個憑證將擁有相同的指紋。 
  
6. 移至 [**憑證**] 視圖之後, 請選擇 [**詳細資料**]。 這可讓您在選取 [ **subject**] 時查看憑證受領人名稱, 並顯示指派的主體名稱和相關聯的屬性。
    
7. 您也需要檢查 [Subject]**替換名稱**專案。 您會發現下列一或多個專案:
    
   - 此池的 [池名稱], 如果這不是「池」, 則是單一伺服器名稱。
    
   - 證書指派的伺服器名稱。
    
   - 簡單的 URL 記錄, 通常是符合和撥入。
    
   - Web 服務內部和 Web 服務外部名稱 (例如 webpool01.contoso.net、webpool01.contoso.com), 根據拓撲建立器和跨 ridden Web 服務選擇中的選擇進行。
    
   - 如果已指定, 則 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄。
    
     如果您有多個指派的憑證, 您必須檢查多個憑證 (請選取上述記事)。
    
8. 因此, 如果您找到 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄, 您已經設定好了。 您可以關閉 MMC。
    
9. 如果未指派, 您必須建立新的憑證要求 (請見上述說明), 或者您必須安裝其後續授權 (我們建議您這麼做的 PowerShell 如下)。
    
## <a name="configure-the-reverse-proxy"></a>設定反向 proxy
<a name="ConfigRP"> </a>

下列步驟並不是完全遵循的步驟。 這是因為在早期版本的產品中, 我們已逐步說明如何設定威脅管理閘道 (TMG), 如果您沒有使用這項功能, 您就必須從該處處理您自己的版本。
  
在 Microsoft 不會再將 TMG 提供給產品, 如果您仍需要進行設定, 您可以查看[Lync Server 2013 的步驟](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)。 但是, 下列資訊的預期更常見, 即使沒有任何辦法, 我們也可以針對每個反向 proxy 提供特定的逐步逐步步驟。
  
我們主要要考慮兩件事:
  
- 您是否要在 HTTPS 上使用初始自動探索要求 (我們建議這麼做)？
    
  - 如果您有 web 發佈規則, 您必須進行修改。
    
  - 如果您還沒有網路發佈規則, 您需要建立它。
    
- 如果您是通過 HTTP 進行初始自動探索要求, 則您也需要建立或修改該規則。
    
> [!NOTE]
> **重要**Proxy 超時值是一個數位, 不會因部署而異。 您應該監視您的部署並修改用戶端最佳體驗的價值。 您可以將值設為 [低] 與200。 如果您是在您的環境中支援 Lync 行動用戶端, 則應該將此值設定為 960, 以允許來自 Office 365 的推播通知超時, 其超時值為900。 您很可能需要增加超時值, 以避免用戶端在值太低時中斷連線, 或在用戶端中斷連線後, 如果透過 proxy 連線, 則將數位減少 (長時間)。 針對您的環境, 監視及設定一般的方式是判斷此值適當設定的唯一正確方法。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>修改外部自動探索 SAN 與 URL 的現有 web 發佈規則

1. 開啟您的反向 proxy 介面。
    
2. 您必須找出您的 web 發佈規則, 然後選擇 [編輯] 選項 (它可能位於功能表或索引標籤上, 視您的反向 proxy 設定而定)。
    
3. 應該有一個區域, 指出該 web 發佈規則的套用位置。 您需要針對內送網站或網站的要求修改這個規則。 您要新增新**** 的專案。
    
4. 輸入自動探索網站的名稱 (我們將使用的範例是 lyncdiscover.contoso.com), 然後根據您的反向 proxy 的格式, 按一下 **[確定] 或 [** **儲存**]。
    
5. 您可能有新的憑證, 且其中有 [自動探索] SAN 專案。 還需要安裝, 並根據您的反向 proxy 設定來設定使用。 完成設定後, 請務必儲存所有專案。
    
6. 如果您的反向 proxy 擁有**測試**功能, 請使用它, 以確保一切正常運作。
    
7. 現在, 如果您的環境中有控制器或主管池, 您可能需要重複這些步驟 (這會表示您有第二個規則)。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>建立外部自動探索 URL 的 web 發佈規則

1. 開啟您的反向 proxy 介面。
    
2. 您需要在介面中尋找您建立 web 發佈規則的位置, 然後選擇 [**新增**] 或 [**建立**] 選項 (可能位於功能表或索引標籤上, 視您的反向 proxy 設定而定)。 您正在尋找建立新的 web 發佈規則的選項。
    
3. 通常, 您必須輸入下列資訊:
    
   - **Name (名稱**): 規則的名稱
    
   - **規則動作**: 在這種情況下, 它是一個**允許**規則, 您可以透過您的反向 proxy 來傳送某個專案。
    
   - 您所選擇的**發佈**規則或選項就是**單一網站或負載平衡器**。
    
   - 這必須是外部存取的**SSL** , 請選擇該選項。
    
   - 您必須發佈**內部發佈**的路徑, 然後在您的前臺端池的負載平衡器 (或控制器池的負載平衡器 (如果有的話) 的 fqdn) 中輸入外部 Web 服務的 fqdn (如果有的話), 就會 sfb_ 範例。pool01。
    
   - 您應該輸入** / *** 作為您要發佈的路徑, 但也必須**轉寄原始主機標頭**。
    
   - 系統會提供**公用或外部名稱**詳細資料或資訊的選項。 您可以在此輸入以下位置:
    
   - **接受要求**, 但它應該用於功能變數名稱。
    
   - 在**名稱**中, 您應該輸入**lyncdiscover。** <sipdomain>(這是外部自動探索服務 URL)。 現在, 如果您是在 [前端] 池上為 [外部 Web 服務] URL 建立規則, 您必須在您的前端池 (例如, lyncwebextpool01.contoso.com) 輸入外部 Web 服務的 FQDN (例如,)。
    
   - 將會有一個**路徑**選項, 您必須在這裡輸入** / ***。
    
   - 您必須使用最新的公用憑證選取**SSL 監聽**程式。
    
   - **驗證委派**應該設定為 [**無委派**], 但**應該**允許直接用戶端驗證。
    
   - 規則應該設定為 [**所有使用者**]。
    
   - 這應該是建立此規則所需的所有資訊, 並可讓您繼續進行。
    
4. 您必須確保**原始主機標頭**已轉寄。
    
5. **網頁伺服器**埠也必須設定, 您必須執行下列動作:
    
   - **將要求重新導向至 HTTP 埠**, 埠號碼應該是**8080**。
    
   - **將要求重新導向至 SSL 埠**, 埠號碼應該是**4443**。
    
6. 完成所有設定之後, 您必須儲存或套用這些專案, 然後您就會想要測試規則。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>建立埠80的網路發佈規則 (選用)

1. 開啟您的反向 proxy 介面。
    
2. 您需要在介面中尋找您建立 web 發佈規則的位置, 然後選擇 [**新增**] 或 [**建立**] 選項 (可能位於功能表或索引標籤上, 視您的反向 proxy 設定而定)。 您正在尋找建立新的 web 發佈規則的選項。
    
3. 通常, 您必須輸入下列資訊:
    
   - **Name (名稱**): 規則的名稱
    
   - **規則動作**: 在這種情況下, 它是一個**允許**規則, 您可以透過您的反向 proxy 來傳送某個專案。
    
   - 您所選擇的**發佈**規則或選項就是**單一網站或負載平衡器**。
    
   - 這必須是**不安全的連線才能連線到已發佈的 Web 服務器或伺服器**陣列。
    
   - 您需要發佈**內部發佈**的路徑, 並輸入您的前臺池負載平衡器之**VIP 位址**的 FQDN, 例如, sfb_pool01 為 [contoso.]。
    
   - 您應該輸入** / *** 作為您要發佈的路徑, 但也必須**轉寄原始主機標頭**。
    
   - 系統會提供**公用或外部名稱**詳細資料或資訊的選項。 您可以在此輸入以下位置:
    
   - **接受要求**, 但它應該用於功能變數名稱。
    
   - 在**名稱**中, 您應該輸入**lyncdiscover。** <sipdomain>(這是外部自動探索服務 URL)。
    
   - 將會有一個**路徑**選項, 您必須在這裡輸入** / ***。
    
   - 您必須選取網頁監聽程式, 或允許您的反向 proxy 為您建立一個。
    
   - **驗證委派**應該設定為 [**無委派**], 但**不應**允許直接用戶端驗證。
    
   - 規則應該設定為 [**所有使用者**]。
    
   - 這應該是建立此規則所需的所有資訊, 並可讓您繼續進行。
    
4. 需要設定**Web 服務器**埠, 您必須執行下列動作:
    
   - **將要求重新導向至 HTTP 埠**, 埠號碼應該是**8080**。
    
   - **將要求重新導向至 SSL 埠**, 埠號碼應該是**4443**。
    
5. 完成所有設定之後, 您必須儲存或套用這些專案, 然後您就會想要測試規則。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>使用混合式部署設定自動探索以進行行動
<a name="ConfigAutoD"> </a>

商務用 Skype Server 的混合式環境是結合內部部署與 O365 環境的環境。 當您在混合式環境中使用商務用 Skype 伺服器時, 自動探索服務必須能夠從上述任一種環境中找出使用者。
  
若要讓行動用戶端發現使用者的位置, 必須使用新的統一資源定位器 (URL) 來設定自動探索服務。 步驟如下:
  
1. 開啟商務用 Skype Server 管理命令介面。
    
2. 執行下列動作以取得商務用 Skype Server 環境的屬性**ProxyFQDN**值:
    
   ```
   Get-CsHostingProvider
   ```

3. 接著, 仍在 [shell] 視窗中執行下列動作:
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    其中 [身分識別] 會以共用的 SIP 位址空間的功能變數名稱取代。
    
## <a name="test-your-mobility-deployment"></a>測試行動部署
<a name="TestMobility"> </a>

一旦您部署商務用 Skype Server 行動服務和商務用 Skype Server 自動探索服務之後, 您就會想要執行測試事務, 以確保您的部署能正常運作。 您可以執行**測試 CsUcwaConference** , 以測試兩位使用者在會議中建立、加入和溝通的能力。 您將需要兩位使用者 (real 或 test) 及完整的認證, 才能執行這項測試。 此命令將適用于商務用 Skype 用戶端和 Lync Server 2013 用戶端。
  
在商務用 Skype Server 2015 上的 Lync Server 2010 用戶端, 您必須執行**測試 CsMcxP2PIM**以進行測試。 您的 Lync Server 2010 使用者仍必須是實際的使用者, 或是預先定義的測試使用者, 您需要其密碼認證。

> [!NOTE]
> MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>針對商務用 Skype 和 Lync 2013 行動用戶端測試會議

1. 在安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的任何電腦上, 以**CsAdministrator**角色的成員的身分登入。
    
2. 啟動**商務用 Skype Server 管理命令**介面 (您可以在 [搜尋] 中輸入名稱, 或 [移至**所有程式**] 並加以選擇)。
    
3. 在命令列中, 輸入:
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   您也可以在腳本中設定認證, 並將其傳遞給 test Cmdlet。 我們有一個範例, 如下所示。
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>測試 Lync 2010 行動用戶端的會議

> [!NOTE]
> MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。

1. 在安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的任何電腦上, 以**CsAdministrator**角色的成員的身分登入。
    
2. 啟動**商務用 Skype Server 管理命令**介面 (您可以在 [搜尋] 中輸入名稱, 或 [移至**所有程式**] 並加以選擇)。
    
3. 在命令列中, 輸入:
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   您也可以在腳本中設定認證, 並將其傳遞給 test Cmdlet。 我們有一個範例, 如下所示。
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

若要進一步回顧命令程式, 您可以查看 CsUcwaConference 和[Test CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)的[測試](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>針對推播通知進行設定
<a name="ConfigPush"> </a>

您可以傳送徽章、圖示或通知等形式的推播通知, 即使 Skype 或 Lync app 不在使用中, 也能傳送到行動裝置。 但什麼是推播通知？ 它們是事件警示, 例如新的或未接的 IM 邀請, 或接收到的語音信箱。 商務用 Skype Server 行動服務將這些通知傳送到雲端型 Skype for business Server 推播通知服務, 然後將通知傳送到 Windows Phone 使用者的 Microsoft 推播通知服務 (MSNS)。
  
此功能不會在 Lync Server 2013 中保持不變, 但如果您有商務用 Skype 伺服器, 您會想要執行下列動作:
  
- 針對商務用 Skype Server Edge 伺服器, 新增新的主機服務提供者、Microsoft 商務用 Skype Online, 然後設定貴組織與商務用 Skype Online 之間的託管提供者同盟。
    
- 執行**CsPushNotificationConfiguration** Cmdlet 來啟用推播通知。 依預設, 推播通知會關閉。
    
- 測試您的同盟設定和推播通知。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>設定您的商務用 Skype Edge 伺服器以取得推播通知

1. [登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。
    
2. 啟動**商務用 Skype Server 管理命令**介面。
    
3. 新增商務用 Skype Server online 主機服務提供者。
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   例如:
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 您不能有一個以上的同盟關聯與單一主機服務提供者。 因此, 如果您已設定與 sipfed.online.lync.com 有同盟關聯的主機服務提供者, 請不要為它新增另一個主機服務提供者, 即使主機提供者的身分識別是 SkypeOnline 以外的其他。 
  
4. 在您的組織與商務用 Skype Online 的 [推播通知服務] 中設定託管提供者同盟。 在命令列中, 您必須輸入:
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>啟用推播通知

1. [登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。
    
2. 啟動**商務用 Skype Server 管理命令**介面。
    
3. 啟用推播通知:
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 啟用同盟:
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>測試同盟與推播通知

1. [登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。
    
2. 啟動**商務用 Skype Server 管理命令**介面。
    
3. 測試同盟設定:
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    例如:
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. 測試推播通知:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    例如:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>設定行動原則
<a name="ConfigMob"> </a>

您可以使用商務用 Skype 伺服器來決定誰可以使用行動服務、透過公司通話、透過 IP (VoIP) 或影片撥打電話, 以及 VoIP 或視頻是否需要 WiFi。 [透過公司通話] 可讓行動使用者在撥打電話和接聽電話時, 使用公司電話號碼, 而不是行動電話號碼。 該行另一端的人員不會看到行動使用者的手機號碼, 而是讓行動使用者避免撥出電話費。 當您設定 VoIP 和影片時, 使用者可以進行 VoIP 通話及進行音訊。 WiFi 使用的設定會決定是否需要使用者的行動裝置, 才能透過行動資料網路使用 WiFi 網路。
  
行動性、透過公司通話, 以及 VoIP 及視頻功能預設為啟用。 已停用 [VoIP] 和 [影片] 的 [需要 WiFi] 設定。 系統管理員能夠變更 (全域、依網站或使用者)。
  
若要能夠使用行動功能及透過公司通話, 使用者必須:
  
- 針對商務用 Skype Server 啟用
    
- 已啟用企業語音功能。
    
- 指派 [ **EnableMobility** ] 選項設定為**True**的行動原則。
    
若要讓使用者能夠透過工作使用通話, 他們也必須:
  
- 已指派已選取 [**啟用同時撥打電話**] 選項的語音原則。
    
- 已指派**EnableOutsideVoice**設定為**True**的行動原則。
    
> [!NOTE]
> 未啟用企業語音的使用者可以使用行動裝置來撥打 Skype VoIP 通話, 或在行動裝置上使用 [按一下以加入] 連結來加入會議 (如果已針對其相關的語音原則設定適當的選項)且. 規劃主題中有更多詳細資料。 
  
### <a name="modify-global-mobility-policy"></a>修改全域行動原則

1. [登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。
    
2. 啟動**商務用 Skype Server 管理命令**介面。
    
3. 輸入以下內容, 即可關閉行動及透過工作全域通話的存取權:
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 您可以透過工作關閉通話, 而不需關閉行動存取權。 但是, 您也無法關閉行動, 也不需要關閉透過工作進行通話。 
  
    如需詳細資訊, 請參閱[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>依網站修改行動原則

1. [登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。
    
2. 啟動**商務用 Skype Server 管理命令**介面。
    
3. 您可以建立網站層級原則、關閉 VoIP 及影片、啟用 [IP 音訊需提供 WiFi], 以及需要 IP 視頻的 WiFi。 輸入
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    深入瞭解[新的 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-user"></a>依使用者修改行動原則

1. [登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。
    
2. 啟動**商務用 Skype Server 管理命令**介面。
    
3. 建立使用者層級行動原則, 並透過使用者的工作關閉行動與通話。 輸入
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    範例資料的進一步範例:
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > 您可以透過工作關閉通話, 而不需關閉行動存取權。 但是, 您也無法關閉行動, 也不需要關閉透過工作進行通話。 
  

