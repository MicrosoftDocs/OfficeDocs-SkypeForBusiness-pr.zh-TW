---
title: 商務用 Skype Server 2019 的容量規劃
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 本節中的主題可協助您瞭解如何規劃及部署商務用 Skype Server，使您可以充分規劃組織中的使用者人數，並規劃其活動所產生的伺服器負載。
ms.openlocfilehash: 090d209d1b60d866ddabe976ffb8b04394712525
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600888"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的容量規劃

本文根據[商務用 Skype Server 中使用者模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)所述的使用方式，提供網站上的使用者人數所需的伺服器數目指導

## <a name="tested-hardware-platform"></a>測試的硬體平臺

我們已在下表所述的硬體上進行效能測試。 我們所有的建議和結果都是以這種硬體為基礎。 如果您決定嘗試使用比您在這裡列出的功能較強大的硬體，請注意，您可能面臨功能問題或效能不良。

**效能測試中所使用的硬體**

|**硬體元件**|**建議**|
|:-----|:-----|
|CPU  <br/> |Intel 至強 E5 2673 v3 雙處理器，6核心，2.4 ghz (GHz) 或更高版本。  <br/> 商務用 Skype Server 2019 角色不支援 Intel Itanium 處理器。  <br/> |
|記憶體  <br/> |32 gb (GB) 。  <br/> |
|磁片  <br/> |可  <br/> •8個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁片磁碟機， (兩個磁片使用 raid 1 和6，使用 RAID 10) 。  <br/> 或  <br/> •固態磁片磁碟機 (Ssd) 能夠為 8 10000 RPM 機械磁片磁碟機提供相同的可用空間及類似的效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡，可使用 1 Gbps 或以上 (2 網路介面卡，但必須以單一 MAC 位址和單一 IP) 位址進行分組。  <br/> 前端伺服器、後端伺服器及 Standard Edition 伺服器 **不** 支援雙重或多穴設定。 <br/> 只要未對作業系統公開，而且正用來監視和管理伺服器硬體，您就可以使用帶外管理系統，例如 DRAC 或 ILO。 此案例不會組成多穴伺服器，而且支援此案例。  <br/> |

## <a name="summary-of-results"></a>結果摘要

下表摘要說明我們的建議。

|**伺服器角色**|**支援的使用者人數上限**|
|:-----|:-----|
|前端集區，包含十六部前端伺服器及後端伺服器，或一對後端伺服器，其 SQL Always On 以提供高可用性。  <br/> |106000同時登入的個別使用者，加上50% 的多點狀態 (MPOP) 代表非行動實例，加上40% 的使用者，以行動為總數，總使用210000端點。  <br/> |
|會議 A/V  <br/> |前端集區所提供的 A/V 會議服務，可支援集區的會議，其為最大的會議大小為250的使用者，且一次只執行一個這類大型會議。  <br/> **附注：** 此外，您可以將個別的前端集區與兩部前端伺服器搭配使用，以主控大型會議，以支援250和1000使用者之間的大型會議。 如需詳細資訊，請參閱[在商務用 Skype Server 中規劃大型會議](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)。 <br/> |
|一部 Edge Server  <br/> |18000並行遠端使用者。  <br/> |
|一個 Director  <br/> |18000並行遠端使用者。  <br/> |
|監控和封存  <br/> |監視和封存前端服務會在每個前端伺服器上執行，而不是在不同的伺服器角色上執行。  <br/> 監視和封存每個仍然需要自己的資料庫存放區。 如果您也執行 Exchange 2013 或更新版本，您可以將封存資料保存在 Exchange 中，而不是放在專用 SQL 資料庫中。  <br/> |
|一個轉送伺服器  <br/> |組合與前端伺服器的轉送伺服器，可在集區中的每一部前端伺服器上執行，並且應該為集區中的使用者提供足夠的容量。 若為獨立轉送伺服器，請參閱本主題稍後的「轉送伺服器」一節。  <br/> |
|一部 Standard Edition 伺服器  <br/> |強烈建議您如果使用 Standard Edition 伺服器來主控使用者，則在[規劃高可用性和嚴重損壞修復](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery)時，一定要使用兩部伺服器（成對使用建議）。 配對中的每一部伺服器都可以主控最多2500個使用者，如果一部伺服器失敗，則剩餘的伺服器可支援容錯移轉案例中的5000使用者。  <br/>  如果您的部署包含大量的音訊或影片流量，則伺服器效能可能會受到每一部伺服器的2500多個使用者的影響。 在此情況下，您應該考慮新增更多的 Standard Edition 伺服器或移至商務用 Skype Server Enterprise Edition。 <br/> |

## <a name="front-end-server"></a>前端伺服器

> [!NOTE]
> 此伺服器角色不支援延伸集區。

在前端集區中，您的集區中每個6660使用者都應該有一部前端伺服器，假設已在集區中的所有伺服器上啟用超執行緒，您使用 SQL Server Express Edition，而且伺服器硬體符合[商務用 Skype Server 2019 的伺服器需求](system-requirements.md)的建議。 一個前端集區中的使用者數目上限為106000，也就是在集區中的所有伺服器上使用 SQL Server Express Edition。 如果網站上的使用者超過106000，您可以部署一個以上的前端集區。

當您考慮前端集區中的使用者人數時，請在與此前端集區相關聯的分支辦公室中，加入位於 Survivable Branch 裝置和 Survivable Branch Server 的任何使用者。

當作用中的伺服器無法使用時，其連線會自動轉接至集區中的其他伺服器。 在具有30000使用者和五部前端伺服器的情況下，如果有一部伺服器無法使用，則您的使用者6000的連線必須轉接至其他四部伺服器。 然後，這四個剩下的伺服器都會有7500位使用者，而不是建議的數目。

如果您已開始使用六部前端伺服器做為30000的使用者，且有一個無法使用，則總計5000使用者必須移至其餘的五台伺服器。 這五部剩下的伺服器會接著每個主機6000使用者，這是建議的範圍。

前端集區中的使用者數目上限為106000。 集區中的前端伺服器數目上限是16。

如果是具有80000使用者的前端集區，則在商務用 Skype Server 中遵循[使用者模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)的一般部署中，16部前端伺服器的效能良好。 設計用來支援嚴重損壞修復容錯移轉的部署假設每兩個成對的前端集區中，最多可裝載53000個使用者，而每個集區都有足夠的前端伺服器以包含兩個集區中的使用者，則必須有一個集區容錯移轉至另一個集區。

根據特定前端集區，具有良好效能的支援使用者數目，可能與這些數目不同，原因如下：

- 前端伺服器的硬體不符合建議。
- 除了使用 SQL Server Express edition 之外，SQL Server 您還可以在每個前端集區中裝載其他使用者。
- 組織的使用量與使用者模型很大不同，例如，如果您有大量會議流量。

下表顯示 IM 和目前狀態的平均頻寬（如使用者模型[中在商務用 Skype Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)中所定義）。

|**每位使用者的平均頻寬**|**每個前端伺服器與6660使用者的頻寬需求**|
|:-----|:-----|
|3-3.75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> 若要改善前端伺服器上歸置 A/V 會議和轉送伺服器功能的媒體效能，您應該在前端伺服器上的網路介面卡上啟用接收端伸縮 (RSS) 。 RSS 可讓伺服器上的多個處理器同時處理內送的封包。 如需詳細資訊，請參閱[Windows Server 2012 檔中的接收端擴充 (RSS) ](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))。 如需如何啟用 RSS 的詳細資訊，您必須參考您的網路介面卡檔。

## <a name="conferencing-maximums"></a>會議最大

給定使用者模型：集區中有5% 的使用者可以在會議中的任何時間，在一段時間內，106000使用者的集區可能會同時在會議中有相關的5300使用者。 這些會議應該是混合媒體 (某些只供 IM 使用的 IM、某些音訊/影片，例如) 和參與者人數。 實際的會議數目不會有硬性限制，而且實際使用量會決定實際的效能。 例如，如果您的組織有許多混合模式會議，而超過使用者模型中的假設，您可能需要部署多部前端伺服器或 A/V 的會議服務器，而不是在本文中找到的建議。 如需使用者模型中假設的詳細資訊，請參閱[商務用 Skype Server 中的使用者模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)。

一般商務用 Skype Server 前端集區所主控的受支援的會議大小上限，也是由250參與者所主控。 當發生 250-使用者會議時，集區仍會同時支援其他會議，例如，總的集區使用者人數為同時召開會議的5%。 例如，在有16部前端伺服器和106000使用者的集區中，當250使用者的會議發生時，商務用 Skype Server 支援5050其他參與小型會議的使用者。

不論位於前端集區或 Standard Edition server 上的使用者數目為何，商務用 Skype Server 至少會支援125其他在主控250使用者會議的集區或伺服器上參與小型會議的使用者。

若要啟用介於250和1000使用者之間的會議，您可以設定個別的前端集區，只是裝載這些會議。 這個前端集區不會裝載任何使用者。 如需詳細資訊，請參閱[在商務用 Skype Server 中規劃大型會議](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)。

如果您的組織的混合模式會議數超過使用者模型中的假設，您可能需要部署的前端伺服器數目超過我們在此檔中建議的數目 (，最多可有16部前端伺服器) 。 如需使用者模型中假設的詳細資訊，請參閱[商務用 Skype Server 中的使用者模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)。

## <a name="edge-server"></a>Edge Server

> [!NOTE]
> 此伺服器角色不支援延伸集區。

您應該針對同時存取網站的每個18000遠端使用者部署一部 Edge Server。 至少我們建議使用兩部 Edge 伺服器以取得高可用性。 這些建議假設 Edge server 的硬體符合 [伺服器硬體平臺](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)的建議。

當您考慮 Edge Server 的使用者人數時，請在與此網站的前端集區相關聯的分支辦公室上，加入位於 Survivable Branch 裝置和 Survivable 分支伺服器的使用者。

> [!NOTE]
> 若要提高 Edge Server 上 A/V 會議 Edge service 的效能，您應該在 Edge Server 上的網路介面卡上啟用接收端伸縮 (RSS) 。 RSS 可讓伺服器上的多個處理器同時處理內送的封包。 如需詳細資訊，請參閱[Windows Server 2012 中的接收方擴充 (RSS) ](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))。 如需如何啟用 RSS 的詳細資訊，您必須參考您的網路介面卡檔。

## <a name="director"></a>Director

> [!NOTE]
> 此伺服器角色不支援延伸集區。

如果您部署 Director 伺服器角色，我們建議您針對同時存取網站的每個18000遠端使用者部署一個 Director。 至少我們建議使用兩個 Director 以取得高可用性。 這些建議假設 Edge server 的硬體符合 [伺服器硬體平臺](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)的建議。

當您考慮 Director 的使用者人數時，請在與此網站的前端集區相關聯的分支辦公室中，加入位於 Survivable Branch 裝置和 Survivable 分支伺服器的使用者。

## <a name="mediation-server"></a>中繼伺服器

> [!NOTE]
> 此伺服器角色不支援延伸集區。

如果您組合轉送伺服器與前端伺服器，則轉送伺服器會在集區中的每一部前端伺服器上執行，並且應該為集區中的使用者提供足夠的容量。

如果您部署獨立的轉送伺服器集區，則要部署的轉送伺服器數目取決於許多因素，包括用於轉送伺服器的硬體、您擁有的 VoIP 使用者數目、每個轉送伺服器集區所控制的閘道對等數目、透過這些閘道的繁忙小時流量，以及繞過轉送伺服器之媒體的呼叫百分比。

下表提供一項指導方針，使轉送伺服器可以處理的並行呼叫數，假設轉送伺服器的硬體符合 [伺服器硬體平臺](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) 中的需求，且已啟用超執行緒功能。 如需轉送伺服器伸縮性的詳細資訊，請參閱[在商務用 Skype Server 中評估轉送伺服器商務用 Skype Server 和部署指導方針](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md)的[語音使用方式和流量](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md)。

下表假設商務用 Skype Server 中的[使用者模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)所匯總的使用方式。

**獨立轉送伺服器容量：70% 內部使用者，30% 具有非旁路通話容量的外部使用者 (轉送伺服器所執行的媒體轉碼)**

|**伺服器硬體**|**呼叫數目上限**|**T1 線路數目上限**|**E1 線數目上限**|
|:-----|:-----|:-----|:-----|
|Intel 至強 E5 2673 v3 雙處理器，6核心，2.4 ghz (GHz) 或更高版本，且 **已停** 用 64 GB 記憶體和單一雙埠網路介面卡。  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Intel 至強 E5 2673 v3 雙處理器，6核心，2.4 ghz (GHz) 或更高版本，含 64 GB 記憶體和一個雙埠網路介面卡。  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> 雖然具有 64 GB 記憶體的伺服器用於效能測試，但獨立的轉送伺服器支援具有 32 GB 記憶體的伺服器，且足以提供此表格所示的效能。

**轉送伺服器容量 (與前端伺服器的轉送伺服器組合) 70% 內部使用者、30% 外部使用者、Non-Bypass 通話容量 (轉送伺服器所執行的媒體處理)**

|**伺服器硬體**|**呼叫數目上限**|
|:-----|:-----|
|Intel 至強 E5 2673 v3 雙處理器，6核心，2.4 ghz (GHz) 或更高版本。，含 64 GB 記憶體和 2 1GB 的網路介面卡卡。  <br/> |200  <br/> |

> [!NOTE]
> 此數位遠遠小於獨立轉送伺服器的號碼。 這是因為前端伺服器除了語音通話所需的其他功能之外，還必須針對其所在的6600使用者處理其他功能和功能。

> [!NOTE]
> 若要改善轉送伺服器的效能，您應該啟用轉送伺服器上網路介面卡上的接收端擴充 (RSS) 。 RSS 可讓伺服器上的多個處理器同時處理內送的封包。 如需詳細資訊，請參閱「[Windows Server 2012 中的接收端擴充](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))。 如需如何啟用 RSS 的詳細資訊，您必須參考您的網路介面卡檔。

## <a name="back-end-server"></a>後端伺服器

雖然大部分的資料庫資訊都會儲存在前端伺服器上，但您應確定後端伺服器是否符合本節先前和 [伺服器硬體平臺](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)中所列的硬體建議。

為了提供後端伺服器的高可用性，我們建議您部署 AlwaysOn 可用性群組或伺服器鏡像。 如需詳細資訊，請參閱[商務用 Skype Server 中的後端伺服器高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。

## <a name="monitoring-and-archiving"></a>監控和封存

如果您部署監控或封存，這些服務的前端功能會在前端伺服器上執行，監控和封存都會使用自己的資料庫存放區，與後端存放區分開。 或者，如果您已部署 Exchange 2013，您可以將立即訊息封存資料儲存在 Exchange 中，而不是在專用的 SQL 存放區中。

下表指出每位使用者每天需要多少資料庫儲存空間，以監控和封存資料。

||**CDR (監控)** <br/> |**QoE (監控)** <br/> |**封存** <br/> |
|:-----|:-----|:-----|:-----|
|每位使用者每天所需的磁碟空間  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft 使用下表中的硬體，以在其效能測試期間監控和封存資料庫伺服器。 測試會收集兩個前端集區的資料，每個集區都包含80000個使用者。

**監視與封存效能測試中所使用的硬體**

|**硬體元件**|**建議**|
|:-----|:-----|
|CPU  <br/> |Intel 至強 E5 2673 v3 雙處理器，6核心，2.4 ghz (GHz) 或更高版本。  <br/> |
|記憶體  <br/> |48 GB  <br/> |
|磁片  <br/> | 可<br/> •4個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間 (磁片應該位於2倍的 RAID 1 設定) 中。 <br/>或 <br/>•固態磁片磁碟機 (Ssd) 能夠為 4 10000 RPM 機械磁片磁碟機提供相同的可用空間及類似的效能。   <br/> |
|網路  <br/> | 1個雙埠網路介面卡，建議使用 1 Gbps 或以上 (2，這需要搭配單一 MAC 位址和單一 IP 位址) 。  <br/> |

**建議的磁片配置**

|**Drive** <br/> |**RAID 設定** <br/> |**磁片數目** <br/> |
|:-----|:-----|:-----|
|單一磁片磁碟機上的 CDR、QoE 及封存資料庫資料檔案  <br/> |1 + 0  <br/> |16   <br/> |
|CDR 資料庫記錄檔  <br/> |1   <br/> |2   <br/> |
|QoE 資料庫記錄檔  <br/> |1   <br/> |2   <br/> |
|封存資料庫記錄檔  <br/> |1   <br/> |2   <br/> |

## <a name="video-interop-server-capacity"></a>影片 Interop 伺服器容量

如果您部署了視頻 Interop 伺服器，但您需要判斷容量，您會看到同時撥打的最大視頻電話會議系統 (VTCs) 數目。 例如，如果您的組織中有 250 VTCs，而且使用者模型估計最多有20% 的使用者可能會同時進行通話，您可以根據50同時 VTCs 的容量規劃。