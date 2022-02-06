---
title: 使用商務用 Skype Server 部署 Lync VDI 外掛程式
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 本主題討論連接至遠端虛擬桌面時使用商務用 Skype 的部署程式。
---

# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>使用商務用 Skype Server 部署 Lync VDI 外掛程式
 
本主題討論連接至遠端虛擬桌面時使用商務用 Skype 的部署程式。 規劃的考慮是在[VDI 環境中規劃商務用 Skype](../../plan-your-deployment/clients-and-devices/vdi-environments.md)。
  
在安全性與合規性問題尤其敏感的某些組織中，會使用 (VDI) 環境的虛擬桌面基礎結構。 他們的使用者位於本機 Windows 電腦上，並使用虛擬機器上的用戶端。 在需要其他 VDI 外掛程式軟體的連接上使用商務用 Skype。
  
有兩個可用於 VDI 外掛程式元件的解決方案，一種是由 Microsoft 提供，另一個是 Citrix 所提供。 Microsoft 建議在新的部署中使用新的 HDX 即時優化套件解決方案，但會繼續支援其生命週期其餘部分的原始 Lync VDI 外掛程式。 
  
本主題提供有關部署 Microsoft Lync VDI 外掛程式的詳細資料，該外掛程式只支援 Windows 7 及 Windows 8 或 Windows Server 2008，而且只支援 Lync 2013 或商務用 Skype 用戶端。 沒有任何計畫可以更新此外掛程式，但是會視需要更新商務用 Skype 的[Citrix HDX 即時優化套件](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>準備您的環境以進行 Lync VDI 外掛程式
<a name="Prepare_vdi"> </a>

1. 在商務用 Skype Server 中，確定所有的 Lync VDI 外掛程式使用者 EnableMediaRedirection 設定為 TRUE。 如需詳細資訊，請參閱 [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) Cmdlet 及 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet 的說明主題。
    
2. 在資料中心伺服器上，將商務用 Skype 用戶端安裝在所有虛擬機器上。
    
3. 在本機電腦上，安裝 Lync VDI 外掛程式。
    
    使用者現在應該將象耳機或網路攝像頭的裝置連接至其本機電腦。
    
## <a name="configure-remote-desktop-connection-settings"></a>設定遠端桌面連線設定
<a name="Prepare_vdi"> </a>

若要準備 Lync VDI 外掛程式的遠端桌面連線，請在本機電腦上執行下列步驟：
  
1. 如果本機電腦正在 Windows 8 執行，請跳過此步驟。 如果本機電腦使用 SP1 執行 Windows 7，請安裝最新的 Windows 8 版本的[遠端桌面服務用戶端](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)。
    
2. 按一下 [ **開始**]，然後按一下 [ **遠端桌面** 連線]，以啟動遠端桌面服務用戶端。
    
3. 按一下 **[選項]**。
    
4. 按一下 [**本機資源**] 索引標籤。在 [**遠端音訊**] 底下，按一下 [**設定**]，然後執行下列動作：
    
   - 在 [ **遠端音訊播放**] 底下，選取 [ **在此電腦上播放**]。
    
   - 在 [ **遠端音訊錄製**] 底下，選取 [不 **錄製**]。
    
   - 按一下 [確定]。
    
5. 按一下 [ **體驗** ] 索引標籤。在 [ **效能**] 下，清除 [ **持續性點陣圖** 快取] 核取方塊。
    
6. 按一下 [**一般**] 索引標籤。在 [**電腦**] 中，輸入虛擬機器的名稱，然後按一下 [**連線**]。 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>在虛擬機器上登入和使用商務用 Skype
<a name="SfB_signin"> </a>

啟用 Lync VDI 外掛程式之後，使用者在虛擬機器上登入商務用 Skype 時請遵循下列步驟。
  
1. 使用者在虛擬機器上的商務用 Skype 用戶端中輸入認證。
    
2. 商務用 Skype 偵測 Lync VDI 外掛程式之後，商務用 Skype 會提示使用者重新輸入認證。 建議使用者在此對話方塊中選取 **[儲存我的密碼]** 核取方塊，這樣在後續的登入中就不需要輸入認證。
    
3. 商務用 Skype 會開始配對 Lync VDI 外掛程式。 在這種情況下，用戶端會在商務用 Skype 狀態列中顯示兩個圖示。 左下方的圖示會指出沒有音訊裝置可用，而右下方的閃爍圖示表示 VDI 配對正在進行中： a。 在 VDI 配對成功後，圖示會變更，以指出將用於通話的音訊裝置和 VDI 配對成功： b。 使用者現在可以在連接至本機電腦的商務用 Skype 相容裝置上看到其狀態，並照常撥打和接聽電話。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI 外掛程式疑難排解
<a name="tshoot_VDI"> </a>

如果您在安裝 Lync VDI 外掛程式之後遇到問題，請參閱下列各節。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>安裝 Lync VDI 外掛程式時的問題

若安裝 Lync VDI 外掛程式時發生問題，請檢查下列各項：
  
- 確定您在 TEMP 和 TMP 系統變數中指定的資料夾中有足夠的空間。
    
- 確定已關閉防寫保護。 如需相關指示，請參閱您的裝置生產商的檔。
    
### <a name="troubleshooting-issues-with-pairing"></a>疑難排解配對問題

當 Lync VDI 外掛程式配對失敗時，右下方的配對圖示會顯示為紅色的 "X"，如下所示： 
  
可能的失敗原因，以及您可以採取以修正問題的動作。 
  
- **使用者在登入時輸入不正確的憑證。**
    
    使用者應登出商務用 Skype，並使用正確的認證重新登入。 配對對話方塊會重新出現，並顯示配對是否成功。
    
- **有另一個遠端桌面用戶端執行個體正在執行中。**
    
    如果他們使用 Windows 中的遠端桌面連線，使用者應執行下列動作：
    
1. 啟動工作管理員：按 **Alt+Ctrl+Delete** 鍵，然後按一下 [啟動工作管理員]。
    
2. 按一下 [程序] 索引標籤，在清單中尋找名為 **mstsc.exe** 的所有程序。
    
3. 將每個 **mstsc.exe** 程序醒目提示，然後按一下 [結束處理程序]。 
    
4. 啟動新的遠端桌面工作階段，並重試連線。 
    
- **必要檔案安裝不正確。**
    
    在本機電腦上安裝外掛程式之後，請檢查這些檔案是否存在於 C:\Program files \ Microsoft Office \Office15 (或適當的磁碟機號) 上：
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **商務用 Skype 用戶端是在本機電腦上執行。**
    
    若要使用 Lync VDI 外掛程式，在本機電腦上不得執行商務用 Skype 用戶端，否則配對會失敗。 最佳作法是，使用者不應該在本機電腦上安裝商務用 Skype 用戶端。
    
## <a name="see-also"></a>另請參閱
<a name="tshoot_VDI"> </a>

[規劃 VDI 環境中的商務用 Skype](../../plan-your-deployment/clients-and-devices/vdi-environments.md)