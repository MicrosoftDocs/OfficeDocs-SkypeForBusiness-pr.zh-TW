---
title: 使用商務用 Skype Server 部署 Lync VDI 外掛程式
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 本主題討論在連線至遠端虛擬桌面時，使用商務用 Skype 的部署程式。
ms.openlocfilehash: f864136ab55f37a9bfaf54d6c31d74d31844da59
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768945"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>使用商務用 Skype Server 部署 Lync VDI 外掛程式
 
本主題討論在連線至遠端虛擬桌面時，使用商務用 Skype 的部署程式。 規劃[針對 VDI 環境中的商務用 Skype](../../plan-your-deployment/clients-and-devices/vdi-environments.md)規劃考慮。
  
虛擬桌面基礎結構（VDI）環境是在安全性與合規性問題特別敏感的一些組織中使用。 其使用者位於本機 Windows 電腦上，且使用虛擬機器上的用戶端。 在需要額外 VDI 外掛程式軟體的連線上使用商務用 Skype。
  
VDI 外掛程式元件（由 Microsoft 提供並由 Citrix 提供）提供兩種方案。 Microsoft 建議您在新的部署中使用新的 HDX 即時優化套件方案，但仍會繼續支援原始的 Lync VDI 外掛程式，以供其生命週期的剩餘部分使用。 
  
本主題提供有關部署 Microsoft Lync VDI 外掛程式的詳細資料，該外掛程式只支援 Windows 7 和 Windows 8 或 Windows Server 2008，且只支援 Lync 2013 或商務用 Skype 用戶端。 沒有任何方案可用於更新此外掛程式，但商務用 Skype 的[CITRIX HDX 即時優化套件](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)會視需要更新。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>為 Lync VDI 外掛程式準備您的環境
<a name="Prepare_vdi"> </a>

1. 在商務用 Skype Server 中，確保所有 Lync VDI 外掛程式使用者的 EnableMediaRedirection 都設定為 TRUE。 如需詳細資訊，請參閱[新版 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) Cmdlet 和[CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet 的說明主題。
    
2. 在資料中心伺服器上，在所有虛擬機器上安裝商務用 Skype 用戶端。
    
3. 在本機電腦上，安裝 Lync VDI 外掛程式。
    
    使用者現在應該將耳機或網路攝像頭等裝置連線至他們的本機電腦。
    
## <a name="configure-remote-desktop-connection-settings"></a>設定遠端桌面連線設定
<a name="Prepare_vdi"> </a>

若要準備 Lync VDI 外掛程式的遠端桌面連線，請在本機電腦上執行下列步驟：
  
1. 如果本機電腦執行的是 Windows 8，請略過此步驟。 如果本機電腦執行的是 Windows 7 與 SP1，請安裝最新的 Windows 8 版本的[遠端桌面服務用戶端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。
    
2. 按一下 [**開始**]，然後按一下 [**遠端桌面**連線]，啟動遠端桌面服務用戶端。
    
3. 按一下 [**選項**]。
    
4. 按一下 [**本機資源**] 索引標籤。在 [**遠端音訊**] 底下，按一下 [**設定**]，然後執行下列動作：
    
   - 在 [**遠端音訊播放**] 底下，選取 [**在這台電腦上播放**]。
    
   - 在 [**遠端音訊錄製**] 底下，選取 [不**錄製**]。
    
   - 按一下 [確定]****。
    
5. 按一下 [**體驗**] 索引標籤。在 [**效能**] 底下，清除 [**永久點陣圖緩存**] 核取方塊。
    
6. 按一下 [**一般**] 索引標籤。在 [**電腦**] 中，輸入虛擬機器的名稱，然後按一下 **[連線]**。 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>在虛擬機器上登入並使用商務用 Skype
<a name="SfB_signin"> </a>

啟用 Lync VDI 外掛程式之後，當您在虛擬機器上登入商務用 Skype 時，使用者會按照下列步驟進行。
  
1. 使用者在虛擬機器上執行的商務用 Skype 用戶端輸入其認證。
    
2. 在商務用 Skype 偵測到 Lync VDI 外掛程式之後，商務用 Skype 會提示使用者重新輸入認證。 在這個對話方塊中，我們建議使用者選取 [**儲存我的密碼**] 核取方塊，以便在進行後續登入時，系統不會要求您輸入認證。
    
3. 商務用 Skype 開始配對 Lync VDI 外掛程式。 在這種情況下，用戶端會在商務用 Skype 狀態列中顯示兩個圖示。 左下角的圖示表示沒有可用的音訊裝置，右下方的閃爍圖示則表示正在進行 VDI 配對： a。 在已成功進行 VDI 配對之後，圖示會變更，以指示將用於通話的音訊裝置和 VDI 配對成功： b。 使用者現在可以在連線至本機電腦的商務用 Skype 相容裝置上看到他或她的目前狀態，並照常撥打及接聽電話。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI 外掛程式疑難排解
<a name="tshoot_VDI"> </a>

如果您在安裝 Lync VDI 外掛程式後遇到問題，請參閱下列各節。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>安裝 Lync VDI 外掛程式的相關問題

如果安裝 Lync VDI 外掛程式時會發生問題，請檢查下列專案：
  
- 確定您在 TEMP 及 TMP 系統變數中指定的資料夾中有足夠的空間。
    
- 確定已關閉 [防寫] 功能。 如需相關指示，請參閱您的裝置製造商的檔。
    
### <a name="troubleshooting-issues-with-pairing"></a>對配對問題進行疑難排解

當 Lync VDI 外掛程式配對失敗時，右下角的配對圖示會顯示為紅色的 [X]，如下所示： 
  
下列是失敗的可能原因，以及您可以採取的動作來修正問題。 
  
- **使用者在登入期間輸入的認證不正確。**
    
    使用者應該登出商務用 Skype，然後使用正確的認證重新登入。 [配對] 對話方塊會再次出現，並顯示配對是否成功。
    
- **遠端桌面用戶端的另一個實例正在執行。**
    
    如果他們是在 Windows 中使用 [遠端桌面連線]，使用者就應該執行下列動作：
    
1. 啟動 [工作管理員]：按**Alt + Ctrl + Delete**，然後按一下 [**啟動工作管理員**]。
    
2. 按一下 [**處理**程式] 索引標籤，然後在清單中尋找所有名為**mstsc**的進程。
    
3. 醒目提示每個**mstsc**程式，然後按一下 [**結束處理**程式]。 
    
4. 啟動新的遠端桌面會話，然後再次嘗試連線。 
    
- **無法正確安裝所需的檔案。**
    
    在本機電腦上安裝外掛程式之後，請檢查以確定這些檔案存在於 C:\Program Files\Microsoft Office\Office15 （或適當的磁片磁碟機號）下：
    
  - LyncVdiPlugin
    
  - UcVdi
    
- **商務用 Skype 用戶端正在本機電腦上執行。**
    
    若要使用 Lync VDI 外掛程式，不一定要在本機電腦上執行商務用 Skype 用戶端，否則配對將會失敗。 最佳做法是，使用者不應該在本機電腦上安裝商務用 Skype 用戶端。
    
## <a name="see-also"></a>另請參閱
<a name="tshoot_VDI"> </a>

[規劃 VDI 環境中的商務用 Skype](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
