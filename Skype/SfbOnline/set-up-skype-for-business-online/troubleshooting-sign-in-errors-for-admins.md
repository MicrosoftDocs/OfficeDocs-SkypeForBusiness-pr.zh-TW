---
title: 系統管理員適用的商務用 Skype 登入錯誤問題疑難排解
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Setup
description: '了解商務用 Skype Online 登入錯誤的常見原因，並對這些問題進行疑難排解。 '
ms.openlocfilehash: 397e899796184274ca357e40e070e7c92cf23b66
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "37642325"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>系統管理員適用的商務用 Skype 登入錯誤問題疑難排解

若要針對商務用 Skype Online 登入錯誤進行疑難排解，請從消除登入困難的最常見原因開始。 如有需要，您可以根據錯誤類型執行特定的解決步驟。 如果使用者仍無法登入，請收集其他資訊，然後尋求其他協助。

## <a name="what-do-you-want-to-do"></a>您要做什麼？
<a name="top"> </a>

> [檢查商務用 Skype Online 登入錯誤的常見原因](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [追蹤特定錯誤的解決步驟 (僅限企業版)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [將 msoidsvc.exe 防火牆項目新增至您的 Proxy 伺服器](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [更新 DNS 設定](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [在您的 ADFS 伺服器上安裝第三方 SSL 憑證](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [更新安全性認證](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [修改 TrustModelData 登錄機碼](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [在 Active Directory 中更新使用者設定](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [使用 Microsoft 支援服務疑難排解指南](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [收集更多資訊並尋求其他協助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>檢查商務用 Skype Online 登入錯誤的常見原因
<a name="toc323194094"> </a>

大部分的登入問題都可以追蹤少數幾個原因，其中許多原因都很易於修正。 下表列出導致登入錯誤的常見原因，以及您或使用者可以採取來加以解決的一些步驟。


| **可能的原因**                                                                                                                                                    | **解決方案**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 登入時會顯示一個對話方塊，內含下列字詞︰**無法針對您的登入地址確認伺服器是否可信任。仍要連線？** <br/> | 確認對話方塊中的網域名稱是您的組織中受信任的伺服器，例如，**domainName.contoso.com**。 要求使用者選取 [永遠信任此伺服器]**** 核取方塊，然後按一下 [連線]****。 <br/> 企業客戶只要修改在每個使用者電腦上的 Windows 登錄，即可以在使用者第一次登入時避免這個訊息出現。 如需詳細資料，請參閱[修改 TrustModelData 登錄機碼](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)。<br/> |
| 登入位址、使用者名稱或密碼輸入錯誤  <br/>                                                                                                               | 確認使用者的登入名稱和密碼正確。 <br/>  驗證使用者的登入名稱格式如下：<strong>bobk@contoso.com</strong>。 這可能與您用來登入組織網路的格式不同。  <br/>  我們可能會要求使用者再次登入。 <br/>                                                                                                                                                                                                                             |
| 忘記密碼  <br/>                                                                                                                                             | 重設使用者的密碼，並通知使用者新的臨時密碼。  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 未獲授權使用商務用 Skype Online  <br/>                                                                                                                  | 確認使用者已註冊為商務用 Skype Online 使用者。 如果沒有，請註冊該使用者，然後要求使用者再次登入。  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| 安裝的商務用 Skype Online 版本錯誤  <br/>                                                                                                           | 此問題通常與包含下列字詞的錯誤訊息相關聯：**驗證服務可能與這一版的程式不相容**。  <br/> 要求使用者從 Office 365 入口網站解除安裝並重新安裝商務用 Skype Online。  <br/>                                                                                                                                                                                                                                                    |
| 取得登入所需的個人憑證時發生問題  <br/>                                                                                           | 如果使用者的登入地址最近已變更，則可能需要刪除快取的登入資料。 要求使用者登出，在登入畫面上按一下 [刪除我的登入資訊] 連結，然後再試一次。  <br/>                                                                                                                                                                                                                                                                                                                                |
| 您設定自訂網域名稱，但是變更可能沒有完全傳佈到系統。  <br/>                                                         | 首先，請確定您已修改網域名稱服務 (DNS) 記錄，以反映變更。  <br/> 如果您已完成必要的 DNS 變更，請建議使用者稍後再嘗試登入。 DNS 變更最多可能需要 72 個小時的時間，才能反映在整個系統中。  <br/>                                                                                                                                                                                                                                                        |
| 系統時鐘與伺服器時鐘不同步  <br/>                                                                                                                     | 確保您的網路網域控制站正在與可靠的外部時間來源同步處理。 如需詳細資訊，請參閱 Microsoft 知識庫文章816042：[如何在 Windows Server 中設定授權時間伺服器](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)。<br/>                                                                                                                                                                                                                                          |

若要針對商務用 Skype Online 登入錯誤進行疑難排解，請從消除登入困難的最常見原因開始。 如有需要，您可以根據錯誤類型執行特定的解決步驟。 如果使用者仍無法登入，請收集其他資訊，然後尋求其他協助。

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>追蹤特定錯誤的解決步驟 (僅限企業版)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  這些指示主要適用於 Microsoft Office 365 方案 E 客戶。 如果您是 Office 365 方案 P 客戶，請繼續閱讀下一節，[收集更多資訊並尋求其他協助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)。

如果您嘗試了上一節中的建議之後，使用者無法登入，您可以根據錯誤類型執行額外的疑難排解。 下表列出最常見的錯誤訊息和可能的原因。 表格之後為解決每個問題的詳細程序。

|**錯誤訊息**|**可能的原因**|**解決方案**|
|:-----|:-----|:-----|
|找不到登入位址  <br/> |來自 Microsoft Online Services 登入小幫手 (msoidsvc) 的登入要求無法透過您的外部防火牆或 Proxy 伺服器進行。  <br/> |[將 msoidsvc.exe 防火牆項目新增至您的 Proxy 伺服器](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|伺服器暫時無法使用  <br/> |如果組織有自訂網域，則必要的網域名稱系統 (DNS) 設定可能遺失或不正確。  <br/> |[更新 DNS 設定](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|伺服器暫時無法使用  <br/> |如果組織使用單一登入與 Active Directory 同盟服務 (ADFS) 搭配，則您可能是使用自我簽署的安全通訊端層 (SSL) 認證，而非第三方憑證授權單位提供的認證。  <br/> |[在您的 ADFS 伺服器上安裝第三方 SSL 憑證](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|取得登入所需的個人憑證時發生問題  <br/> |如果您已移除用於登入的快取伺服器資料，但錯誤持續出現，則使用者的安全性認證可能已損毀，或使用者電腦上的 RSA 資料夾可能封鎖驗證。  <br/> |[更新安全性認證](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|使用者第一次登入時出現憑證信任對話方塊。  <br/> |如果您的商務用 Skype 伺服器尚未列在 **TrustModelData ** 登錄機碼中，就會顯示這個對話方塊。 <br/> |[修改 TrustModelData 登錄機碼](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|使用者未啟用 SIP  <br/> |如果組織具有 Microsoft Office Communications Server 或 Microsoft Lync Server 2010 的舊版安裝，您可能未在將伺服器解除委任之前從伺服器刪除使用者。 因此，**msRTCSIP-UserEnabled** 屬性仍會在 Active Directory 網域服務中設定為 **FALSE**。 <br/> |[在 Active Directory 中更新使用者設定](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>將 msoidsvc.exe 防火牆項目新增至您的 Proxy 伺服器
<a name="add-a-firewall"> </a>

此程序為下列錯誤訊息的可能修正方式：**找不到登入位址**。

> [!NOTE]
> 下列步驟假設您使用 Forefront Threat Management Gateway (TMG) 2010。 如果您有不同的網頁閘道解決方案，請使用以下步驟 4 中所述的設定。


若要在 Forefront TMG 2010 中建立 Msoidsvc.exe 的應用程式項目，請遵循這些步驟：

1. 在 Forefront 的左窗格中，按一下 [網路]****。

2. 按一下 [網路]**** 索引標籤。在右窗格的 [任務]**** 索引標籤下，按一下 [設定 Forefront TMG 用戶端設定]****。

3. 在 [Forefront TMG 用戶端設定]**** 對話方塊中，按一下 [新增]****。

4. 在 [應用程式項目設定]**** 對話方塊中，設定下列規則：

|**應用程式**|**機碼**|**值**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

如需詳細資訊，請參閱 Microsoft 知識庫文章2409256：[因為內部部署防火牆封鎖連線，您無法連線至商務用 Skype Online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)。

### <a name="update-dns-settings"></a>更新 DNS 設定
<a name="update-dns-service"> </a>

如果您的組織有自訂網域，則此程序為下列錯誤訊息的可能修正方式：**伺服器暫時無法使用**。

- 如需如何將下列 CNAME 記錄新增至網域的相關資訊，請與您的網域名稱註冊機構連絡：

  - **DNS 記錄類型**：CNAME

  - **名稱 **：sip

  - **值/目的地**：sipdir.online.lync.com

如需詳細資訊，請參閱 Microsoft 知識庫文章 2566790：[對 Office 365 中的商務用 Skype Online DNS 設定問題進行疑難排解](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)。

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>在您的 ADFS 伺服器上安裝第三方 SSL 憑證
<a name="verify-upn-and"> </a>

若要在您的 Active Domain Federation Services (ADFS) 伺服器上安裝第三方 SSL 憑證，請按照下列步驟操作：

1. 從第三方憑證授權單位 (例如 VeriSign 或 Thawte) 取得 SSL 憑證。

2. 使用 ADFS 管理主控台在您的 ADFS 伺服器上安裝憑證。

### <a name="update-security-credentials"></a>更新安全性認證
<a name="update-security-credentials"> </a>

此程序為下列錯誤訊息的可能修正方式：**取得登入所需的個人憑證時發生錯誤**。

若要消除可能的憑證或認證問題，請先在 Windows 憑證管理員中更新使用者的憑證。 若要這樣做，請執行下列步驟：

1. 開啟 Windows 憑證管理員。 若要執行此動作，請依序按一下 [開始]**** 及 [執行]****，並輸入 **certmgr.msc**，然後按一下 [確定]****。

2. 按兩下 [個人]****，然後按兩下 [憑證]****。

3. 依 [發行者]**** 欄排序，然後尋找 Communications Server 所核發的憑證。

4. 以滑鼠右鍵按一下憑證，然後按一下 [刪除]****。

接下來，如果使用者執行的是 Windows 7，請在 Windows 認證管理器中移除其儲存的認證。 若要這樣做，請執行下列步驟：

1. 依序按一下 [開始]****、[控制台]**** 然後按一下 [認證管理員]****。

2. 尋找用來連線至商務用 Skype Online 的認證集。

3. 展開認證集，然後按一下 [從保存庫移除]****。

4. 再次登入，然後重新輸入使用者的認證。

最後，如果使用者在您更新其認證後仍無法登入，請嘗試刪除使用者電腦上的 RSA 資料夾，因為這可能會封鎖使用者驗證程序的完成：

1. 使用系統管理員帳戶登入使用者的電腦。

2. 如有需要，請將資料夾檢視選項 [顯示隱藏的檔案]**** 開啟。

3. 在檔案總管的網址列中輸入以下內容：**C:\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**，其中的 ***UserName*** 為您的 Windows 登入名稱。

4. 刪除具有名稱 **S-1-5-21-** 後面接著數字字串的任何資料夾。

### <a name="modify-trustmodeldata-registry-keys"></a>修改 TrustModelData 登錄機碼
<a name="modify-trustmodeldata-registry"> </a>

當使用者第一次登入時，可能會收到包含以下內容的對話方塊：**無法針對您的登入地址確認伺服器是否可信任。仍要連線?** 這是安全性功能，而不是錯誤。 不過，您可以在使用者第一次登入之前，使用群組原則物件 (GPO) 來更新使用者的電腦以加上您的網域名稱，以避免此對話方塊顯示。 若要這麼做，請執行下列動作：

- 建立並部署一個可將商務用 Skype 網域名稱 (例如 domainName. contoso) 附加到 HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData 的目前值的 GPO。

> [!IMPORTANT]
>  您必須將您的網域名稱*附加*到現有值，而非只是將它取代。

如需詳細資訊，請參閱 Microsoft 知識庫文章 2531068：[商務用 Skype (Lync) 無法針對您的登入地址確認伺服器是否可信任](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)。

### <a name="update-user-settings-in-active-directory"></a>更新 Active Directory 中的使用者設定
<a name="update-user-settings"> </a>

如果組織具有 Microsoft Office Communications Server 或 Microsoft Lync Server 2010 的舊版安裝，您可能未在將伺服器解除委任之前從伺服器刪除使用者。 因此，**msRTCSIP-UserEnabled** 屬性仍會在 Active Directory 網域服務中設定為 **FALSE**。

若要修正此問題，請遵循下列步驟：

1. 將所有受影響使用者的 **msRTCSIP-UserEnabled** 屬性更新為 **TRUE**。

2. 重新執行 Microsoft Online Services 目錄同步作業工具 (DirSync)。 如需詳細資訊，請參閱[整合您的內部部署目錄與 Azure Active Directory](https://technet.microsoft.com/zh-TW/library/hh967642.aspx)。

若要針對商務用 Skype Online 登入錯誤進行疑難排解，請從消除登入困難的最常見原因開始。 如有需要，您可以根據錯誤類型執行特定的解決步驟。 如果使用者仍無法登入，請收集其他資訊，然後尋求其他協助。
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>使用 Microsoft 支援服務疑難排解指南
<a name="toc325626447"> </a>

如果仍無法解決使用者的登入問題，請檢閱 Microsoft 知識庫文章 2541980 中的建議：[如何疑難排解 商務用 Skype 中的登入問題](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980) (英文)。

## <a name="collect-more-information-and-seek-additional-help"></a>收集更多資訊並尋求其他協助
<a name="collect-more-information"> </a>

如果您已按照上述指示進行，但仍無法解決您的登入問題，則必須收集其他資訊並與技術支援人員連絡。 若要這樣做，請執行下列步驟：

1. 從使用者的電腦取得記錄檔和 Windows 事件記錄詳細資料。 如需逐步指示，請參閱使用者說明主題[開啟 Lync 的錯誤記錄](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)。

2. 將關於錯誤的記錄檔和詳細資訊傳送給 Microsoft 技術支援人員。

我們可能會要求您在受影響使用者的電腦上安裝 Online Services Diagnostic and Logging (MOSDAL) 支援工具組，藉此提供額外的診斷資訊。 如需詳細資訊，請參閱[使用 MOSDAL 支援工具組](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)。

若要針對商務用 Skype Online 登入錯誤進行疑難排解，請從消除登入困難的最常見原因開始。 如有需要，您可以根據錯誤類型執行特定的解決步驟。 如果使用者仍無法登入，請收集其他資訊，然後尋求其他協助。

## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)


