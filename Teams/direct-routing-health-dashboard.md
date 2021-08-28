---
title: 直接路由的健康情況儀表板
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何使用健康情況儀表板監控會話邊界控制器與直接路由之間的連接。
ms.openlocfilehash: aec8a0bb37af02f6103714a26c9d35e18879985c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592337"
---
# <a name="health-dashboard-for-direct-routing"></a>直接路由的健康情況儀表板

直接路由健康情況儀表板可讓您監控會話邊界控制器 (SBC) 與直接路由介面之間的連接。  您可以使用健康情況儀表板監控 SBC、電話語音，以及 SBC 與直接路由介面之間的網路參數相關資訊。 這項資訊可協助找出問題，包括通話中斷的原因。 例如，如果 SBC 上的憑證已過期或網路問題，SBC 可能會停止傳送通話。 請參閱 [系統管理員角色](using-admin-roles.md) ，以瞭解誰可以存取健康狀態儀表板。

健康情況儀表板會監控兩層資訊：

- 已連接 SBC 的整體健康情況
- 已連接 SBC 的詳細資訊

您可以在系統管理中心Microsoft Teams健康商務用 Skype儀表板。

## <a name="overall-health"></a>整體健康情況

健康情況儀表板提供與連結 SBCs 整體健康情況相關的下列資訊：

 ![顯示健康狀態儀表板統計資料](media/direct-routing-dashboard-stats1.png)

- **直接路由摘要** - 顯示在系統中註冊的 SBCs 總數。 註冊表示租使用者系統管理員使用 New-CsOnlinePSTNGateway 新增 SBC。 如果 SBC 是在 PowerShell 中新增，但從未連結過，健康情況儀表板會顯示為不健康狀態。

- **SBC** - 配對 SBC 的 FQDN。

- 網路 **效能比 (NER**) - NER 會測量已傳送的通話數與傳送給收件者的通話數，以測量網路進行通話的能力。  

   NER 會測量網路將通話傳送至遠端終端機的能力，但不包括導致通話拒絕的使用者動作。  如果收件者拒絕通話或將通話傳送至語音信箱，則通話會視為成功傳遞。 這表示接聽訊息、忙碌訊號或沒有接聽的鈴聲都被視為成功通話。
  
   例如，假設直接路由傳送呼叫給 SBC，而 SBC 會傳送 SIP 代碼"504 Server Time out - 伺服器嘗試存取另一個伺服器以嘗試處理要求，而且沒有收到提示回應」。 此回應表示 SBC 端有問題，這將會減少此 SBC 的健康儀表板上的 NER。
  
   由於您採取的動作可能取決於受影響的通話數量，因此健康情況儀表板會顯示分析的通話數，以計算參數。 如果通話數小於 100，則 NER 可能相當低，但仍然正常。

   用來計算 NER 的公式為：

   NER = 100 x (通話 + 使用者忙碌 + 響鈴沒有接聽 + 終端拒絕) /通話總數

- **平均通話持續時間** - 關於平均通話持續時間的資訊可協助監控通話品質。 1：1 PSTN 通話的平均持續時間為 4 到 5 分鐘。  不過，每家公司的平均值可能會有所不同。  Microsoft 建議為貴公司的平均通話持續時間建立比較基準。 如果此參數明顯低於比較基準，表示您的使用者有通話品質或可靠性問題，且掛斷時間早于平常。 如果您開始看到極低的平均通話持續時間 ，例如 15 秒，來電者可能會因為服務無法可靠地執行而掛斷電話。

   由於您採取的動作可能取決於受影響的通話數量，因此健康情況儀表板會顯示分析的通話數，以計算參數。

- **TLS** 連接狀態 - TLS (傳輸層安全性) 連接會顯示直接路由與 SBC 之間的 TLS 連接狀態。 健康狀態儀表板也會分析憑證到期日，並警告憑證是否設定在 30 天內到期，以便系統管理員在服務中斷前更新憑證。

   按一下警告訊息，即可在右邊的快顯視窗中查看詳細的問題描述，以及修正問題的建議。

- **SIP 選項狀態** – 根據預設，SBC 會每分鐘傳送選項訊息。 此組配置可能會因不同的 SBC 廠商而異。 直接路由會警告未傳送或未進行配置的 SIP 選項。 有關 SIP 選項監控的詳細資訊，以及 SBC 可標示為無法運作的情況，請參閱監控和疑難排解 [直接路由](direct-routing-monitor-and-troubleshoot.md)。

- **詳細的 SIP 選項狀態** - 除了顯示 SIP 選項流程有問題之外，健康情況儀表板也會提供錯誤的詳細描述。 您可以按一下 「警告」訊息來存取描述。 右側快顯視窗會顯示詳細的錯誤描述。

   SIP 選項狀態訊息的可能值如下：

    - 使用中 - SBC 為使用中--Microsoft Direct 路由服務會定期看到選項。

    - 警告，沒有 SIP 選項 - 會話邊界控制器存在於資料庫中 (系統管理員使用 New-CsOnlinePSTNGateway 命令建立) 。 它已配置為傳送 SIP 選項，但直接路由服務從未看到從此 SBC 返回的 SIP 選項。

    - 警告，未配置 SIP 訊息 - 未開啟使用 SIP 選項的主幹監控。 Microsoft 通話系統使用 SIP 選項和傳輸層安全性 (TLS) 握手監控，以在應用程式層級偵測已連接的會話邊界控制器 (SBC) 健康情況。 如果這個主幹可以在網路層級 (ping) ，但憑證已過期或 SIP 堆疊無法工作，就會發生問題。 為了協助及早找出這類問題，Microsoft 建議啟用傳送 SIP 選項。 檢查您的 SBC 製造商檔以設定傳送 SIP 選項。

- **同時通話容量** - 您可以使用 -MaxConcurrentSessions 參數的 New 或 Set-CsOnlinePSTNGateway 命令，指定 SBC 可以處理的並行通話限制。 此參數會計算直接路由使用特定 SBC 傳送或接聽的通話數，並將它與限制集進行比較。 注意：如果 SBC 也處理不同 PBX 的通話，此號碼不會顯示實際的同時通話。

## <a name="detailed-information-for-each-sbc"></a>每個 SBC 的詳細資訊

您也可以查看特定 SBC 的詳細資訊，如下列螢幕擷取畫面所示：

![健康情況儀表板 SBC 詳細資料](media/direct-routing-dashboard-SBC-detail1.png)

詳細視圖顯示下列其他參數：

- **TLS 連接狀態** – 這是與 「整體健康情況」頁面上相同的度量;

- **TLS Connectivity 上次狀態** ： 顯示 SBC 與直接路由服務建立 TLS 連接的時間;

- **SIP 選項狀態** – 與 「整體健康情況」頁面上的相同度量單位。

- **上次檢查 SIP 選項** 的時間 ：上次收到 SIP 選項的時間。

- **SBC 狀態** – SBC 的整體狀態，以所有受監控參數為基礎。

- **同時通話**- 顯示 SBC 已處理的並行通話數。 這項資訊很實用，可預測您需要的並行通道數目，並查看趨勢。 您可以根據天數滑動資料，以及輸入/ (/所有) 。

- **網路參數** - 所有網路參數都是從直接路由介面到會話邊界控制器測量。 有關建議值的資訊，請參閱準備貴組織的網路[Microsoft Teams，並](./prepare-network.md)查看 Customer Edge 以Microsoft Edge建議的值。

   - 抖動 – 是使用 RTCP 在兩個端點之間計算網路傳播延遲時間變化的毫秒 (RTP 控制通訊協定) 。

   - 封包遺失 – 是未送達的封包量值;這是在兩個端點之間計算。

   - 延遲 - (也稱為往返時間) 是訊號的接收時間長度，加上接收該訊號所花的時間長度。 此延遲時間是由訊號兩點之間的傳播時間所組成。

   您可以根據天數滑動資料，以及輸入/ (/所有) 。

**網路效能比** - 這是出現在整體健康情況儀表板上的相同參數，但可以選擇以時間系列或通話方向來分割資料。