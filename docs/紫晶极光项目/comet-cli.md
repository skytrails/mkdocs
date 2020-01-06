# comet-cli

```bash
# comet-cli -c updateslotmap —cartaddr 104 -n 1 -l Amethystum_ZL600_E0600169003 —seataddr 3001 -T 25G_RE_S
# comet-cli -c updateslotmap —cartaddr 104 -n 1 -l Amethystum_ZL600_E0600169003 —seataddr 3001 -T 25G_RE_S
```

- ## 关闭系统文件校验

```bash
# comet-cli -c updatecometconf --MW_ARCHIVER.SKIP_VERIFY 1
# comet-cli -c updatecometconf --BurnConfig.enableChunk 0
# comet-cli -c updatecometconf --BurnConfig.enableRRC 0
```

