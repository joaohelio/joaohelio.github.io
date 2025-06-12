# System Capacity Calculator

A calculator for estimating system infrastructure requirements based on user load and usage patterns.

## 📋 Features

### Input Parameters
- **Daily Active Users (DAU)** - Number of unique users active per day
- **Monthly Active Users (MAU)** - Number of unique users active per month
- **Session Patterns** - Average sessions per user and requests per session
- **Data Requirements** - Storage needs per user and response sizes
- **Performance Settings** - Cache hit rates and peak traffic multipliers

### Capacity Estimates
- **🔥 Throughput** - Peak RPS, database QPS, and cache-optimized backend load
- **💾 Storage** - Total storage with replication and backup considerations
- **⚡ Cache** - Memory requirements for optimal performance
- **🌐 Network Bandwidth** - Peak and average bandwidth with cache optimization
- **📊 System Summary** - Engagement metrics and architectural recommendations

## 🎯 Use Cases

- **Startup Planning** - Estimate infrastructure costs before launch
- **Scaling Decisions** - Plan capacity upgrades based on growth projections
- **Architecture Reviews** - Validate system design assumptions
- **Cost Estimation** - Calculate cloud infrastructure requirements
- **Performance Planning** - Size caches, databases, and CDNs appropriately


## Calculation Methods

**Throughput Calculations:**
- Peak RPS = (DAU × Sessions × Requests × Peak Multiplier) / (24 × 3600)
- Database QPS = Peak RPS × 2.5 (accounts for complex queries)
- Effective RPS = Peak RPS × (1 - Cache Hit Rate)

**Storage Calculations:**
- Base Storage = MAU × Data per User
- With Replication = Base × 3 (master + 2 replicas)
- With Backups = Replicated × 1.5 (backup overhead)

**Cache Calculations:**
- Cache Size = DAU × Data per User × 0.3 (30% of active data)
- Includes 20% overhead for metadata and fragmentation

**Bandwidth Calculations:**
- Daily Transfer = Requests × Response Size
- Peak Bandwidth accounts for 70% network efficiency
- Cache reduces bandwidth by hit rate percentage

### Key Assumptions
- 20% safety margin for unexpected load spikes
- 15% of DAU are concurrent users during peak hours
- Database queries are 2.5x API requests (complex operations)
- Network efficiency of 70% due to protocol overhead
- Cache stores 30% of active user data for optimal hit rates

## 🌐 Deployment

### GitHub Pages (Recommended)
1. Fork or clone this repository
2. Enable GitHub Pages in repository settings
3. Set source to main branch
4. Access via `https://your-username.github.io/repository-name/`

### Local Development
```bash
# Clone the repository
git clone https://github.com/your-username/system-capacity-calculator.git

# Navigate to directory
cd system-capacity-calculator

# Open in browser
open index.html
```

## 📊 Example Calculations

### Small Application
- **Input**: 10K DAU, 50K MAU, 3 sessions/day, 20 requests/session
- **Output**: ~7 RPS peak, 1.5 GB storage, 10 Mbps bandwidth

### Medium Application
- **Input**: 100K DAU, 500K MAU, 5 sessions/day, 30 requests/session
- **Output**: ~521 RPS peak, 18 GB storage, 156 Mbps bandwidth

### Large Application
- **Input**: 1M DAU, 5M MAU, 4 sessions/day, 25 requests/session
- **Output**: ~3,472 RPS peak, 180 GB storage, 1.04 Gbps bandwidth

⭐ **Star this repository if you find it helpful!**

Made with ❤️ for the developer community