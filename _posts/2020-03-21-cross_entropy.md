# Entropy
> When Shannon asked von Neumann what he should call his information theory by, von Neumann said that he should call it entropy because that is what the formula is in statistical mechanises, but more important, nobody knows what entropy is!



__Table of Contents__

* TOC
{:toc}
</div>

</div>


## Surprisal

**Surprisal**: $ - \frac{1}{log(p)} $

```python
#collapse_hide
sns.set(style="darkgrid")

probability = np.arange(0.01, 1.00, 0.01)
surprisal = -np.log2(probability)

df = pd.DataFrame(dict(x=probability,y=surprisal))

ax = sns.lineplot(x="x", y="y",data=df)
ax.set(xlabel='Probability', ylabel='Surprisal')

ax.annotate(
'The sun will rise tommorow -not surprising', xy=(1.0,0), xytext=(0.6, 1),size='small',
arrowprops=dict(facecolor='black', shrink=0.05)
)

ax.annotate(
'The world will end tommorow - very surprising', xy=(0,6), xytext=(0.1,6),size='small',
arrowprops=dict(facecolor='black', shrink=0.05)
)

plt.show()
```


![png](/images/cross_entropy_files/output_4_0.png)


## Entropy

**Entropy**: $ - \sum_{i=1}^{n} p_i \frac{1}{log(p_i)} $
