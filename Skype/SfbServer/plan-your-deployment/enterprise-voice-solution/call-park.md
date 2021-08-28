---
title: 在商務用 Skype 中規劃通話駐留
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 在商務用 Skype Server 企業語音中規劃通話駐留，讓通話保持通話，並將通話轉接至部門。 包括容量規劃、支援的通話，以及支援的用戶端。
ms.openlocfilehash: 8bc69bedfd3abf7745ce25133ae8ac32d1eda032
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625175"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>在商務用 Skype 中規劃通話駐留
 
在商務用 Skype Server 企業語音中規劃通話駐留，讓通話保持通話，並將通話轉接至部門。 包括容量規劃、支援的通話，以及支援的用戶端。
  
通話駐留應用程式可讓企業語音使用者執行下列作業：
  
- 進行暫止通話，然後從相同電話或其他電話取得通話。
    
- 進行暫止通話，將其轉接至部門或一般區域 (例如，移至銷售部門或存在公共區域電話的倉庫) 。
    
- 保留通話，並將原始接聽電話保留空閒狀態供其他電話使用。
    
當使用者公園通話時，商務用 Skype Server 會將來電轉接至暫時號碼（稱為軌道），在此呼叫會保留，直到被取回或超時為止。商務用 Skype Server 會將軌道傳送給停用通話的使用者。 若要取得寄存通話，使用者可以撥打軌道號碼，或按一下 [交談] 視窗中的 [軌道] 連結或按鈕。 
  
停用通話的使用者可以使用外部機制（如立即訊息 (IM) 或分頁系統）來通知人員取得通話，以與其他人溝通軌道號碼。 停用通話的使用者可以讓 [交談] 視窗保持開啟，以在檢索來電時收到通知。
  
因為軌道範圍是全域唯一的，所以如果路由設定正確，可以從任何商務用 Skype Server 的網站或 PBX 電話中取得通話。 如果沒有人在可設定的時間內取回通話，則呼叫會傳回寄存其的人員。 如果此人沒有回答回電，則會將來電轉接至 fallback 目的地（例如，如果已設定，則為操作員）。 您可以設定來電響鈴的次數，再從一到十次轉接。 如果沒有人接聽轉接的電話，則通話會中斷連線。 檢索或中斷通話呼叫時，會釋放軌道。
  
當您部署通話駐留時，您必須保留駐留通話的分機號碼範圍。 這些分機必須是虛擬分機：沒有指派使用者或電話的分機號碼。 然後，您可以使用分機號碼範圍設定通話駐留軌道表格，並指定哪些應用程式服務主控處理每個範圍的通話駐留應用程式。 每個前端集區在對應的後端伺服器上都有一個呼叫駐留表，用來管理集區上寄存的呼叫。 軌道範圍的清單儲存在中央管理存放區中，用來將軌道式路由傳送至目的地集區。 在其中部署及設定通話駐留應用程式的每個商務用 Skype Server 集區，都可以有一個或多個軌道範圍。 軌道範圍在整個商務用 Skype Server 部署中必須是全域唯一的。 
  
您也可以設定其他通話駐留設定，例如，在通話超時的位置，以及電話上的人員是否會在寄存時，是否會聽到音樂。 您也可以在通話處於保留狀態時，指定要播放的音樂檔案。
  
> [!NOTE]
> 如果上傳至集區的檔案損毀、損毀或已被清除，則不會將通話駐留的自訂封存暫止檔案備份為商務用 Skype Server 嚴重損壞修復程式的一部分。 請永遠為通話保留，保留您為通話保留所上傳之自訂音樂暫止檔案的個別備份副本。 
  
通話駐留應用程式是企業語音的元件。 當您部署企業語音時，會自動安裝及啟用通話駐留應用程式。 不過，企業語音管理員必須設定它，並透過語音原則為使用者啟用通話駐留，您才能使用通話駐留。
  
## <a name="deployment-and-requirements"></a>部署和需求

當您部署企業語音時，會自動安裝通話駐留應用程式。 您可以透過設定語音原則來啟用通話駐留。
  
### <a name="software-requirements"></a>軟體需求

部署通話駐留的所有前端伺服器和 Standard Edition 伺服器都必須為執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器安裝 Windows 媒體格式執行時間，以供執行 Windows Server 2008 R2 的伺服器或 Microsoft Media Foundation 使用。 針對 Windows Server 2008 R2，Windows Media Format Runtime 是以 Windows 桌面體驗的一部分安裝。 Windows媒體格式執行時間或 Microsoft media Foundation 是 Windows 媒體音訊的必要 (。呼叫駐留的 wma) 檔案會對等候音樂播放。
  
### <a name="port-requirements"></a>連接埠需求

通話駐留應用程式使用 **埠 5075**  進行 SIP 聆聽要求。
    
> [!NOTE]
> 此連接埠為預設設定，可使用 **Set-CsApplicationServer** Cmdlet 予以變更。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。
  
### <a name="audio-file-requirements"></a>音訊檔需求

通話駐留應用程式僅支援 Windows 媒體音訊 () 檔案用於等候音樂。 您可以使用 Microsoft Expression Encoder 4 自訂等候音樂的檔案。 若要下載運算式編碼器4，請參閱   ["運算式編碼器 4"](https://go.microsoft.com/fwlink/p/?linkId=202843)。 使用此工具可將檔案轉換成 .wma 格式。 通話駐留等候音樂檔案的建議格式為 Media Audio 9、44 kHz、16 位元、Mono、CBR、32 kbps。
  
> [!NOTE]
> 轉換後的檔案只能以 16 kHz 音頻在電話中播放，即使檔案是以 44 kHz 音頻錄製也一樣。 
  
## <a name="supported-clients-and-calls"></a>支援的用戶端和通話

通話駐留支援下列用戶端和通話類型
  
### <a name="clients-supported-for-parking-calls"></a>支援駐留通話的用戶端

來自任何 IP、專用交換機 (PBX) 、公用交換電話網路 (PSTN) 或行動電話可以寄存的電話。
  
> [!NOTE]
> 只有音訊通話可以寄存。 立即訊息和會議無法停用。 
  
下列用戶端可以將通話駐留用於駐留通話：
  
- 商務用 Skype
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> 行動電話無法將通話駐留用於寄存通話。 
  
### <a name="clients-supported-for-retrieving-calls"></a>支援檢索呼叫的用戶端

軌道範圍會設定為不需要指派使用者或電話) 的虛擬分機區塊 (擴充。 當您將軌道式設定為虛擬分機時，行動電話和 PSTN 電話便無法檢索寄存的呼叫。
  
同盟使用者無法檢索寄存的呼叫。
  
下列用戶端可以檢索寄存在通話駐留上的通話：
  
- 商務用 Skype
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP 公共區域電話
    
- 連接至商務用 Skype Server 基礎結構的非 IP 電話，包括通用區域電話和專用交換機 (PBX) 電話
    
## <a name="call-park-capacity-planning"></a>通話駐留容量規劃

下表說明您可以用來作為容量規劃需求基礎的通話駐留使用者模型。
  
> [!IMPORTANT]
> 請記住，針對嚴重損壞修復容量規劃，配對集區的每個集區都應該可以處理兩個集區中的通話駐留服務工作負載。 
  
**通話駐留使用者模型**

|**計量**|**每個前端伺服器集區  <br/>  (8 部前端伺服器)**|**根據 Standard Edition 伺服器**|
|:-----|:-----|:-----|
|駐留率  <br/> |每分鐘 8 個  <br/> |每分鐘 1 個  <br/> |
|擷取駐留通話率  <br/> |每分鐘 8 個  <br/> |每分鐘 1 個  <br/> |
|平均駐留持續時間  <br/> |60 秒  <br/> |60 秒  <br/> |
   

