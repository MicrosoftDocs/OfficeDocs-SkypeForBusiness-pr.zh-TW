---
title: 在商務用 Skype 中規劃電話寄存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 在商務用 Skype Server Enterprise Voice 中規劃通話寄存, 這可讓通話保持通話, 並將通話轉移至部門。 包括容量規劃、支援的通話, 以及支援的用戶端。
ms.openlocfilehash: 3272efe89ac995b304d96ad7ce5660144641073b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187768"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>在商務用 Skype 中規劃電話寄存
 
在商務用 Skype Server Enterprise Voice 中規劃通話寄存, 這可讓通話保持通話, 並將通話轉移至部門。 包括容量規劃、支援的通話, 以及支援的用戶端。
  
通話駐留應用程式可讓企業語音使用者執行下列動作:
  
- 保留通話, 然後從同一個電話或另一個電話取回通話。
    
- [保留通話] 可將來電轉接到部門或一般區域 (例如, 移至 [銷售部門] 或 [有共同區域電話的倉庫])。
    
- 保留通話, 並保留原始的應答電話供其他通話。
    
當使用者公園來電時, 商務用 Skype 伺服器會將來電轉接到暫時號碼 (稱為軌道), 通話會一直留在進行檢索或超時。商務用 Skype 伺服器會將軌道傳送給停用通話的使用者。 若要取得寄存通話, 使用者可以撥打軌道編號, 或按一下交談視窗中的 [軌道] 連結或按鈕。 
  
停用通話的使用者可以使用外部機制 (例如立即訊息 (IM) 或分頁系統), 通知某人使用外部機制來取得通話, 以將軌道編號傳達給其他人。 停用通話的使用者可以讓交談視窗保持開啟, 在檢索通話時接收通知。
  
由於軌道範圍是全域唯一的, 因此, 如果路由設定正確, 就可以從任何商務用 Skype Server 網站或 PBX 電話中檢索通話。 如果沒有人在可設定的時間內檢索呼叫, 來電會傳回寄存該通話的人。 如果該人員不接聽 ringback, 則會將來電轉接到回退目的地, 例如, 如果已設定, 就會傳送給接線員。 您可以將呼叫響鈴的次數設定為從1到十次轉接。 如果沒有人接聽轉接來電, 通話就會中斷連線。 檢索或斷開通話時, 會釋放軌道。
  
當您部署 [通話寄存] 時, 您必須為 [停止通話] 保留延伸號碼的範圍。 這些延伸必須是虛擬延伸: 沒有指派使用者或電話的延伸。 接著, 您可以將 [通話駐留軌道] 表格設定為延伸的範圍, 並指定哪個應用程式服務主持處理每個範圍的通話駐留應用程式。 每個前端池在對應的後端伺服器上都有一個 [呼叫駐留] 資料表, 用來管理停在該池中的呼叫。 軌道範圍清單會儲存在中央管理存放區中, 並用於將軌道式路由到目的地池。 部署及設定通話駐留應用程式的每個商務用 Skype 伺服器池都可以有一或多個軌道範圍。 在商務用 Skype Server 部署中, 軌道範圍必須全域唯一。 
  
您也可以設定其他通話寄存設定, 例如, 如果電話被重新導向, 以及手機上的人員是否會聽到音樂, 請在停用時撥打。 您也可以指定在通話保留期間播放音樂檔案。
  
> [!NOTE]
> 在商務用 Skype Server 災害復原程式中, 不會將通話駐留的自訂音樂保留式檔案備份, 如果上傳至該池的檔案遭到損毀、損毀或清除, 就會遺失。 針對通話駐留, 請務必針對您上傳的自訂音樂保留檔案保留一個單獨的備份複本。 
  
通話駐留應用程式是企業語音的元件。 當您部署企業語音時, 通話寄存應用程式會自動安裝並啟用。 不過, 在您可以使用電話寄存前, 企業語音管理員必須設定它, 並透過語音原則為使用者啟用它。
  
## <a name="deployment-and-requirements"></a>部署與需求

當您部署企業語音時, 會自動安裝通話駐留應用程式。 您可以透過設定語音原則來啟用通話駐留。
  
### <a name="software-requirements"></a>軟體需求

部署通話駐留的所有前端伺服器和標準版伺服器, 都必須針對執行 Windows Server 2008 R2 的伺服器安裝 windows Media 格式執行時間, 或執行 Windows Server 2012 或 Windows Server 的伺服器的 Microsoft Media Foundation2012 R2。 針對 Windows Server 2008 R2, Windows Media 格式執行時間已安裝為 Windows 桌面體驗的一部分。 Windows media 音訊 (.wma) 檔案需要 windows Media Format 執行時間或 Microsoft 媒體基礎, 這些檔案會通話駐留的暫停播放。
  
### <a name="port-requirements"></a>埠需求

通話駐留應用程式使用**埠 5075**進行 SIP 偵聽要求。
    
> [!NOTE]
> 此埠是預設設定, 您可以使用**CsApplicationServer** Cmdlet 進行變更。 如需此 Cmdlet 的詳細資訊, 請參閱 Lync Server 管理命令介面檔。
  
### <a name="audio-file-requirements"></a>音訊檔需求

通話駐留應用程式只支援 Windows Media 音訊 (.wma) 檔案, 以供等候音樂。 您可以使用 Microsoft Expression 編碼器4來自訂等候音樂的檔案。 若要下載運算式編碼器 4, 請參閱「[運算式編碼器 4](https://go.microsoft.com/fwlink/p/?linkId=202843)」。 使用工具將檔案轉換為 .wma 格式。 通話駐留音樂保留盤案的建議格式是媒體音訊9、44 kHz、16位、單聲道、CBR、32 kbps。
  
> [!NOTE]
> 已轉換的檔案只能在 16 kHz 的電話上播放, 即使該檔案是在 44 kHz 錄製。 
  
## <a name="supported-clients-and-calls"></a>支援的用戶端和通話

通話駐留支援下列用戶端和呼叫類型
  
### <a name="clients-supported-for-parking-calls"></a>支援停用通話的用戶端

來自任何 IP、私人分支 exchange (PBX)、公用交換電話網絡 (PSTN) 或行動電話的呼叫都可以停用。
  
> [!NOTE]
> 只有音訊通話可以停用。 無法停用立即訊息和會議。 
  
下列用戶端可以使用通話駐留撥出電話:
  
- 商務用 Skype
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 助理
    
- Lync Phone Edition
    
> [!NOTE]
> 行動電話無法使用通話駐留撥出電話。 
  
### <a name="clients-supported-for-retrieving-calls"></a>支援的用戶端檢索通話

軌道範圍是設定為虛擬延伸的區塊 (不含指派使用者或電話的延伸)。 當您將 [軌道式] 設定為 [虛擬延伸] 時, 行動電話和 PSTN 手機無法取得停用的通話。
  
同盟使用者無法取得停用的通話。
  
下列用戶端可以檢索寄存在通話寄存上的通話:
  
- 商務用 Skype
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 助理
    
- Lync Phone Edition
    
- IP 通用區域電話
    
- 連線至商務用 Skype Server 基礎結構的非 IP 電話, 包括通用的局域網和私人分支 exchange (PBX) 電話
    
## <a name="call-park-capacity-planning"></a>通話駐留容量規劃

下表說明您可以用來做為容量規劃需求基礎的通話駐留使用者模型。
  
> [!IMPORTANT]
> 請記住, 對於災難復原容量規劃, 配對池的每個池都應該能夠處理兩個池中的通話駐留服務的工作負荷。 
  
**通話駐留使用者模型**

|**衡量**|**每個前臺端<br/>池 (含8個前端伺服器)**|**每個標準版 server**|
|:-----|:-----|:-----|
|公園工資率  <br/> |每分鐘8筆  <br/> |每分鐘1  <br/> |
|檢索暫停的通話頻率  <br/> |每分鐘8筆  <br/> |每分鐘1  <br/> |
|平均公園持續時間  <br/> |60秒  <br/> |60秒  <br/> |
   

