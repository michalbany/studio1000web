<template>
    <button
      :class="computedClass"
      :disabled="disabled"
      role="button"
    >
      <slot />
    </button>
  </template>
  
  <script setup lang="ts">
  import { computed } from 'vue';
  
  // Typy pro varianty, velikosti a props
  type Variant = 'default' | 'destructive' | 'outline' | 'secondary' | 'ghost' | 'link';
  type Size = 'default' | 'sm' | 'lg' | 'icon-sm' | 'icon';
  
  // Definování props s typovou ochranou
  const props = withDefaults(defineProps<{
    variant?: Variant;
    size?: Size;
    disabled?: boolean;
  }>(), {
    variant: 'default',
    size: 'default',
    disabled: false,
  });
  // Základní třídy a varianty
  const baseClass = "inline-flex items-center justify-center gap-2 rounded-md text-sm font-medium ring-offset-background transition-colors transition-shadow focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2";
  
  const variants = {
    variant: {
      default: "bg-red-600 text-white hover:bg-red-600/90 shadow-button",
      destructive: "bg-orange-500 text-white hover:bg-orange-500/90",
      outline: "border border-input bg-background hover:bg-slate-400 hover:text-white",
      secondary: "bg-slate-800 text-white hover:bg-slate-800/80",
      ghost: "hover:bg-transparent hover:text-white",
      link: "text-red-600 underline-offset-4 hover:underline",
    },
    size: {
      default: "h-10 px-4 py-2",
      sm: "h-9 rounded-md px-3",
      lg: "h-11 rounded-md px-8",
      "icon-sm": "h-9 w-9",
      icon: "h-10 w-10",
    },
    disabled: {
      true: "pointer-events-none opacity-50",
    },
  };
  
  // Výpočet výsledné třídy tlačítka
  const computedClass = computed(() => {
    const variantClass = variants.variant[props.variant || 'default'];
    const sizeClass = variants.size[props.size || 'default'];
    const disabledClass = props.disabled ? variants.disabled.true : '';
  
    return `${baseClass} ${variantClass} ${sizeClass} ${disabledClass}`;
  });
  </script>
  <style scoped>
  .shadow-button:hover {
    box-shadow: 0px 0px 15px 0 rgba(220, 38, 38);
  }
  </style>