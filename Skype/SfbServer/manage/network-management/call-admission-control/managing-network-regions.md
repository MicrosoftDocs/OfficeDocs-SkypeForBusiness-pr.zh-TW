---
title: 管理網路地區
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 網路地區 * 是網路中樞或骨幹，用於設定通話許可控制、E9-1-1 和媒體旁路。
ms.openlocfilehash: 5bfe3051404b41cd6a1d96bfac240e83070bbdbc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759735"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>管理商務用 Skype Server 中的網路地區

「網路區域」是用於通話許可控制、E9-1-1 及媒體旁路設定的網路中樞或骨幹。 使用下列程序可以檢視、建立或修改網路區域。 例如，您已為一個語音功能建立網路區域，便不需要建立新的網路區域；其他的進階 Enterprise Voice 功能會使用那些相同的網路區域。 不過，您必須修改現有的網路區域定義，以套用功能特定的設定。 例如，您已為 E9-1-1 (其不需要相關的中央網站) 建立網路區域，而您接著要部署通話許可控制，您便必須修改網路區域定義來指定中央網站。 

使用本文中的程式來查看網路地區資訊，或建立、修改或刪除網路地區。 

## <a name="view-network-region-information"></a>查看網路地區資訊 


網路地區會與跨多個地理區域的網路不同部分交互連線。 每個網路地區都必須與中央網站產生關聯。 中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。 您可以使用商務用 Skype Server 控制台來查看網路地區。 網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。 請使用本主題檢視現有的網路地區。 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台查看網路區域的相關資訊

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區**]。

4.  在 **[地區]** 頁面上，按一下您要檢視的區域。
  
    > [!NOTE]  
    > 您一次僅可檢視一個區域。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路地區資訊

您可以使用 Windows PowerShell 和 **Get-CsNetworkRegion** Cmdlet 來查看網路地區資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 

### <a name="to-view-network-region-information"></a>若要查看網路地區資訊

  - 若要查看所有網路區域的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：
    
    **Get-CsNetworkRegion**
    
    如此將傳回類似如下的資訊：
    
    身分識別：太平洋西北部<br/>
    描述：<br/>
    BypassID：3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    CentralSite： Site： Redmond1<br/>
    BWAlternatePaths： {BWPolicyModality = 音訊;AlternatePath = True， <br/>
                       BWPolicyModality = 影片;AlternatePath = True}<br/>
    NetworkRegionID：太平洋西北部<br/>

如需詳細資訊，請參閱 [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) Cmdlet 的說明主題。


## <a name="create-or-modify-network-regions"></a>建立或修改網路地區 

網路地區會與跨多個地理區域的網路不同部分交互連線。 每個網路地區都必須與中央網站產生關聯。 中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。 您可以使用商務用 Skype Server 控制台設定網路地區。 網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。 您可以從商務用 Skype Server 控制台建立、修改或刪除網路地區。 使用此主題可建立及修改網路地區。 

### <a name="to-create-a-network-region"></a>建立網路地區

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區**]。

4.  在 [ **地區** ] 頁面上，按一下 [ **新增**]。

5.  在 [ **新地區** ] 頁面的 [ **名稱** ] 欄位中輸入值。 此值在您的商務用 Skype Server 部署中必須是唯一的。

6.  從 [ **中央網站** ] 下拉式清單中，選取這個網路地區的中央網站。

7.  根據預設，會選取 [ **啟用音訊替代路徑** ] 核取方塊。 此欄位會決定當主要路徑中不存在足夠的頻寬時，是否會透過替代路徑來路由傳送音訊通話。 只有在您需要關閉對網際網路的卸載時，才清除此核取方塊。 如果您的任何呼叫都是網際網路通話，則必須勾選此核取方塊（不論頻寬設定為何）。

8.  預設會選取 [ **啟用影片替代路徑** ] 核取方塊。 此欄位會決定當主要路徑中不存在足夠的頻寬時，是否會透過替代路徑來路由傳送影片。 只有在您需要關閉對網際網路的卸載時，才清除此核取方塊。 如果您的任何呼叫都是網際網路通話，則必須勾選此核取方塊（不論頻寬設定為何）。

9.   (選用) 在 [ **描述** ] 欄位中輸入值，以提供無法獨立以名稱表示的此地區的詳細資訊。

10. 按一下 **[認可]**。

**關聯的網站** 資料表不會用來建立網路地區。 當您建立或修改網站時，會將網站與區域產生關聯。 如需詳細資訊，請參閱 [管理網站的通話許可控制](managing-call-admission-control-for-sites.md)。

### <a name="to-modify-a-network-region"></a>若要修改網路地區

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區**]。

4.  在 [ **地區** ] 頁面上，按一下您要修改的地區。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 [ **編輯地區** ] 頁面上，您可以修改啟用和停用音訊和影片替代路徑的設定，以及變更描述 (如需詳細資訊，請參閱本主題前面的「建立網路地區」一節。

7.  按一下 **[認可]**。

您無法在此頁面上修改 **相關聯的網站** 。 會提供相關網站的清單以供參考，因此當您修改地區設定時，您就會知道哪些網站會受到影響。


## <a name="delete-existing-network-regions"></a>刪除現有的網路地區 

網路地區會與跨多個地理區域的網路不同部分交互連線。 每個網路地區都必須與中央網站產生關聯。 中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。 您可以使用商務用 Skype Server 控制台設定網路地區。 網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。 您可以從商務用 Skype Server 控制台建立、修改或刪除網路地區。 使用此主題可刪除現有的網路地區。 

### <a name="to-delete-a-network-region"></a>若要刪除網路地區

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區**]。

4.  在 [ **地區** ] 頁面上，按一下您要刪除的地區。
  
    > [!NOTE]  
    > 您可以一次刪除一個以上的區域。 若要執行此動作，請按住 CTRL 鍵並選取多個區域，並按住 CTRL 鍵。 或者，若要選取所有區域，請按一下 [**編輯**] 功能表上的 [全 **選**]。

5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]。


    > [!WARNING]  
    > 如果網路地區與網路網站相關聯，則無法加以移除。 如果您嘗試移除與網站相關聯的區域，您會收到錯誤訊息。 若要查看是否有任何網站相關聯的區域，請選取該區域，然後按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。


## <a name="see-also"></a>另請參閱

[管理網路地區路由](managing-network-region-routes.md)

[New-CsNetworkRegion](/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink)